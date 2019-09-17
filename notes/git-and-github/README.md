# git + github notes

so there are two things to differentiate between here, [git](http://git-scm.com/) && [GitHub](https://github.com/), git is a version control system or VCS ( aka revision control ) command line application. a VCS is essentially a way of creating snapshots ( “committed” changes ) of ur code while u work on it && keep it in a history. u can also create “branches” ( versions or alternate narratives--if u will--to this history ). GitHub is a website which serves a few purposes, including [1] functioning as a backup for ur project, [2] lets u share ur code w/the world in an organized manner && [3] makes it easy to collaborate w/others on code based projects.

git comes w/it’s own unique vernacular which is important to understand before moving fwd ( it’s too easy to get lost in the lingo ) besides “version control” && “command line” there’s also:

- **repository**: also colloquially referred to as a “repo”, is essentially what u call a “versioned” project ( the main difference between a regular project && a versioned project being that there’s a hidden .git folder keeping track of all ur changes, && thus it’s “versioned” )

- **add**: adds a file to ur “stage”, only the files in on stage will be included in ur version history.

- **commit**: this is essentially a “snapshot” of what ur code base looks like at that moment, it’s how u “save” on github, think of it as a point in ur project’s history timeline.

- **push**: if ur repo is hosted on github ( not just versioned w/git on ur computer ) u can update ur github backup by uploading ur latest commits using the push command.

- **branch**: this is like a parallel timeline in ur history. many users will have a “dev” ( or developing ) branch where they’re working on new features && they’ll keep their “master” ( the mian/initial timeline ) only as up to date w/the tested/functioning features. branches are useful for collaboration. there can be more than one user authorized to work on a repo, keeping separate branches can help keep things organized.

- **merge**: this is what u call it when a branch’s changes get’s applied to another branch ( ex: when u “merge” ur dev branch into ur master branch, or when a collaborator working on her branch merges her changes into the group’s master branch )

- **clone**: git's word for "copying" a repository ( different from "downloading" a project from github, which won't include that .git folder, ie. the versioned history )

- **fork**: when a project is “open-source” && hosted on github there’s the potential for anyone to collaborate on the project, but this doesn’t mean they have access to commit/push to the repo ( that would be chaos, && open-source is anything but ) instead what u can do is “clone” ur own version of that repo into a separate repository hosted on ur own account. ur version would be a “fork” of the original repo.

- **pull request**: say u’ve made some impressive changes to a project that u forked && u think it should be incorporated into the main project’s repository, u can send them a special message ( this is the “pull request” ) to the original repo’s owners which lets them know u’ve made some important changes they should consider including into the original repo.

- **remote**: what u call a backup copy of ur repo somewhere else on the Internet. it's common to have a remote backup (typically on a site like github or bitbucket, though u could back it up to ur own server using something like gitlab)

now that ur familiar w/the basic language, u’re ready to start versioning. first thing u want to do is create a repository, i think this is easiest on github by clicking the big green “new repository” button. there u can give it a name && description. u’ll also have the choice to make it public or private. rather than starting an empty repo it’s best to start it ( ie. initialize it ) w/a README file ( this is a markdown file w/ur projects basic info ) + might also help to start a .gitignore10 +/or a license

*SIDE NOTE:* u can learn markdown basics [John Gruber](http://daringfireball.net/projects/markdown/basics)'s page ( Gruber along w/ [Aaron Swartz](https://en.wikipedia.org/wiki/Aaron_Swartz) developed markdown ) +/or check out github's [reference](https://help.github.com/articles/getting-started-with-writing-and-formatting-on-github/).

once created, copy the repo cloning URL && in ur terminal ( in the directory u want ur project to be ) type `git clone UR_COPIED_URL` && it'll clone ur repo ( readme, lisence && all ) to ur laptop.

u might not want to have ur project on github just yet, if that's the case u can turn any local project into a repo in the command line, assuming ur present working directory ( pwd ) is that of the project u want to version, run `git init` to initiatlize the repo. then later when u want to back it up to github, u can create a repo on github ( don't initialize w/a README this time ) && then take the git URL it creates && back in ur terminal run `git add remote UR_GIT_URL`

now ur ready to start versioning! assuming u're in the same directory as the git project, below is a simple versioning workflow:

*if it's the first time u use git ( after installing it ), not a bad idea to do a little [setup]( if it's the first time u use git ( after installing it ), not a bad idea to do a little setup first ) first*

- `git status` checks the current state of the local repo ( are there any new files to stage? was an older file modified? or deleted?). not necessary to do this, but useful ( try it between each of the following steps ).

- `git add filename.html`
"stage" a file to be commited ( any new file or modified file ), u can stage any/all, `git add -A` will add everything that's new/modified. if u want to undo a staging use `git reset`

- `git commit -m "message goes here"`
creates a "snapshot" of the present state of the repo, includes a message that xplains what u added/changed this time around

- `git push origin master`
push ur local changes to ur upstream public repository, in this case ur specifically pushing whichever branch ur currently on locally ( u can check which branch ur own by `git branch` ) to ur master branch on github.

**Check out the Atom "[fligth manual](https://flight-manual.atom.io/using-atom/sections/github-package/)" for instrutions on how to use the Git/GitHub features integrated into the code editor itself**

that’s just the tip of the iceberg, i recommend spending 15mins to go through the [try.github.io](https://try.github.io/levels/1/challenges/1) interactive tutorial ++ there’s lots more beyond that to learn along the way. check out github’s [help](https://help.github.com/) page as well as their [guides](https://guides.github.com/) for more info.

for more on how to participate in Open Source culture check out GitHub's [Open Source Guides](https://opensource.guide/).
