demo-empty-repository
=====================

Git encourages you to work locally a mojority of the time. The distributed nature of it means that you have a fully functional copy of the entire repository on your machine at all times. Unlike Subversion, the server is really secondary to the system and serves more as a convenient syncing mechanism for teams.

Starting Locally
---------------

Sometimes when we start a project the Git repository may not be setup. We can start without source control, but we lose a lot of flexibility and safety in doing so. Because Git is always local starting up a new repository on your machine is extremely easy. From the command line you can navigate into a directory representing your project and run:

`git init`

The directory can either be empty or contain files. Run a status check on the directory to see the new repository in place:

`git status`

At this point there is a fully functional Git repository setup in the directory with a single branch named *master*. If the directory was empty you should see output like the following:

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
