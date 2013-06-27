Git requires you to work locally a majority of the time. The distributed nature of it means that you have a fully functional copy of the entire repository on your machine at all times. Unlike Subversion, the server is really secondary to the system and serves more as a convenient syncing mechanism for teams.

Starting Locally
---------------

Sometimes when we start a project the Git repository may not be setup. We can start without source control, but we lose a lot of flexibility and safety in doing so. Because Git is always local starting up a new repository on your machine is extremely easy. From the command line you can navigate into a directory representing your project and run:

`git init`

The directory can either be empty or contain files. Run a status check on the directory to see the new repository in place:

`git status`

At this point there is a fully functional Git repository setup in the directory with a single branch named `master`. If the directory was empty you should see output like the following:

    # On branch master
    #
    # Initial commit
    #
    nothing to commit (create/copy files and use "git add" to track)

From this point forward you can use Git to add, commit, branch, and merge just as you would with a repository connected to a server. The difference is that you cannot *pull* or *push* since this repository has no remote definition to do those operations to.

Connecting Remotely
-------------------

Let's say you've been diligently working for a week or more and your other team members responsible for source control now have a repository setup out on GitHub. You can of course clone that repository to somewhere and copy and paste your files into it to integrate your work (and honestly, that may be the best approach in some cases). Another option is to connect your local repository to the newly create remote repository using the *remote* command. 

`git remote add --track master origin git@github.com:laughlin/repository-name.git`

There's quite a bit going on in that one line, so let's break down the pieces a bit:

1. **git remote add** (telling git to add a remote reference):<br/>There are a number of different commands you can run using the `remote` command in git. To add a new remote definition to the repository you use the `add` command and provide it a name for the remote reference (typically 'origin') and the URL  for it.

2. **--track master** (telling git to merge your master with the remote master):<br/>This is optional, but will save you work and confusion later on once the remote connection is established. This line essentially tells git to treat the `master` branch on the server and the `master` branch in your local repository as the same and to merge `origin/master` with your local `master` during pull operations.

3. **origin** (telling git the name of your remote reference):<br/>Most Git repositories use `origin` as the remote reference. You can name it whatever you wish and you can have as many remote references as you wish.

4. **git@github.com:musicfuel/demo-empty-repository.git** (telling git the URL of the remote repository):<br/>This is the URL that git will use to push and pull information to and from.
