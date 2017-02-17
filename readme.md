# Josh's janky git tutorial

We're gonna break some stuff, and have fun all the while.

# Contributor Names

_This section is begging for a merge conflict. So lets do it. (see "pull requests" below)_

- Josh Thompson
- your name here


## Order of operations

Here's how we'll spend some time:
- repos. name them silly things.
- remotes. Name them silly things.
- change remote URLs, name them sillier things
- branches. (make them dumb)
- adding and committing
- modify this document.
- delete our master branch, because why not?
- make a pull request. (oh, and re-add our master branch)


### Make a new repo

Make a new repo with a sorta awkward name. Perhaps _because_josh_said_so_ or something like that.

`mkdir` a new folder on your computer for it to live in. Please know that you'll delete this folder at the end of today.

`cd` into that folder, and `git init`.

run `git remote add origin <your_url>`

### Awkward Remote Names

next, run `git remote add smelly_socks <your_url>`

run `git remote -v`

now do `git remote add sooper_smelly_socks <your_url>`

WTF, right?

LMK when you've done this.

lets clean up a bit. Run `git remote -v`. ugly and smelly, so clean that isht up:

`git remote rm smelly_socks`

`git remote rm sooper_smelly_socks`

`git remote rm origin`

Are you seeing a pattern? "git remote" isn't anything special. It's just telling git "whatever comes next is related to remote things"

and whatever comes _after_ "git remote" is just telling git what to do.

> yo git, add something that I'm gonna call "smelly_socks", and here's the URL for that: git@github.com:josh-works/git_practice.git

Now, when you say "smelly socks", git knows what URL you're talking about.

### Change remote URLs

OK, more. re-add your origin URL, but don't call it origin. call it `<yourname_origin>`

so, I'd say:

`git remote add josh_origin git@github.com:josh-works/git_practice.git`

run `git remote -v` to make sure everything is as expected.

Cool. Now, go to your git repo, and change its name (somewhere in "settings"). It'll change the URL. Knowing what we have now worked through above, can you fix your now-broken remote URL?

### Branching

run `git branch`

what branches do you see?

Probably just one. do `git checkout holy_snaps_its_a_branch`. what happens?

Probably some sort of error. turns out you need a `-b` flag when making a new branch.

try `git checkout -b holy_snaps_its_a_branch`. (Whoever reads this first - interrupt me and ask me about tab autocomplete for branches. Yeah, you. reading this right now.)

run `git branch` again. Two branches, right? cool.

Make five more. I kid you not. Five more.

Once you have, take a screenshot of that part of your terminal, and post it to the #git_workflow channel in the turing slack.

delete those branches. Git will let you. If it doesn't, figure out why. Post to the #git_workflow the command you're using to delete a branch.

Deleted them? cool.

Make a new one. You're actually gonna change this one. That leads us to...

### Adding and Committing for Fun and Profit

lets make some changes and see what happens there.

run `curl http://ohshitgit.com/ -o ohshitgit.html`

now `cat ohshitgit.html`

You front-enders should be all over this. To my untrained eye it looks like cryptic and mysterious ... html.

run `git status`. What do you see?

use the instructions to track them untracked files. but don't commit them yet.

run `git status` again. should be green, saying "stuff ready to be committed..."

commit it.

run `git remote -v`. If you have anything in there named `origin`, remove it. Make sure the only results in `git remote -v` is something crazy. here's mine:

![funky dance moves](https://cl.ly/1k1l1n1E2u3S/1____turing_spikes_git_practice__bash_.jpg)

now, open up your repo in your browser. Should look pretty bare.

back to the terminal:

`git push funky_dance_moves master`

suh-weet.

now, we did all this stuff on the master branch, which is a no no. So, do it again.

### Deleting your master branch

checkout a new branch. name it something... distinctive.

run `curl http://www.nosweatshakespeare.com/resources/shakespeare-insults/ -o insults.html`

if you copied and pasted that command, note the spelling error. fix it.

`cat` the file, take a peek. Cool, huh?

add and commit this stuff. check your repo online. do you see any of these changes?

prob not. back to the terminal:

do something exciting:

`git br -d master`

You just deleted your master branch. lolz. I'm writing and making this up as I go. It would be awkward if this wasn't fixable, huh?

`git push <your_crazy_remote_name> <your_current_branch_name>`

Here's what I entered:

`git push funky_dance_moves new-branchy-branch`

checkout your repo. anything interesting?

Your master branch might still be there. let's _really_ delete it.

`git branch -a` => shows remote branches. (Think of `-a` as "all")

hm... I cannot figure out how to delete that branch from the command line.

nbd.

Finish this out by creating a master branch again, checking it out, and using `git merge <crazy_branch_name> master`

Then delete all the non-master branches.

Fix your remotes too. rename your repo to `origin`, and delete the other name.

Ping the slack group when you're done.

### Pull Requests and Merging stuff

CD out of your test git repo, and make another one that has the same name as the repo you're reading from right now.

FORK my repo. Don't clone it, fork it. This will make a copy on your github profile. (Don't worry, you can delete it later)

Clone the forked repo from YOUR profile to the new folder you just made that has its same name.

use your adding remote skills to set it as your remote repo. something like

`git remote add my_forked_copy <url_to_your_fork>` will do it.

Now, add another remote pointing to MY copy!

you can use this string exactly, but type it in yourself, except the URL:

`git remote add joshs_repo git@github.com:josh-works/git_practice.git`

run `git remote -v` and you'll see both. baller, right?

now, checkout a new branch. something like `git checkout -b <myname_additions>` will do fine.

`cd` into the `put_stuff_here` directory, read the readme, and follow the instructions.

now, once you're happy, do `git push joshs_repo <my_branch_name>`

open up my repo in the UI, and we'll walk through this pull request.

You should see something like this:

![pull request](https://cl.ly/392I3S1Q3b0C/josh-works_git_practice__a_repo_that_MUST_evolve_exclusively_with_outside_help_.jpg)

follow the instructions to create a pull request.

Let me know when you've done this. You're cruising.

I'll stop here. If we cover all of this, I think we're doing OK.


### Misc topics

- What happens when you `git commit` with no `-m`? What is this hellscape you see? nbd: it's vim, and hit `:q!` to escape and try again.
- eff. How do I un-f**k this... [oh shit git](http://ohshitgit.com/)
- Pretty terminal colors. What's up there? [quick-and-dirty git autocomplete](https://gist.github.com/josh-works/83fc75e684b4dd2d52b385a67ced4d9b)
- that wasn't enough terminal stuff. Give me more. [here be dragons](https://gist.github.com/josh-works/7f2e6c82d22dca6e9fbc029c8b17703d)
- ACK I `git init`'ed where I shouldn't have. ndb: `rm -rf .git`
- Ack, I made changes on my `master` branch! nbd: `git stash`, `git co -b new_branch`, `git stash pop`.
