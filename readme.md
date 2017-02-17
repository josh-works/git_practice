# Josh's janky git tutorial

We're gonna break some stuff, and have fun all the while.

## Order of operations

Here's how we'll spend some time:

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

> yo git, add something that I'm gonna call "smelly_socks", and here's the URL for that

Now, when you say "smelly socks", git knows what URL you're talking about.

### Change remote URLs

OK, more. re-add your origin URL, but don't call it origin. call it `<yourname_origin>`

so, I'd say:

`git remote add josh_origin git@github.com:josh-works/git_practice.git`

run `git remote -v` to make sure everything is as expected.

Cool. Now, go to your git repo, and change its name. It'll change the URL. Knowing what we have now worked through above, can you fix your now-broken remote URL?
