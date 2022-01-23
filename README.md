# miiifyapp

Simple demo app which uses [annotorious](https://github.com/recogito/annotorious) to annotate images which are stored to a git repo using [Miiify](https://github.com/nationalarchives/miiify). Some examples use the [GitHub CLI](https://github.com/cli/cli) to show how to fork a repo and create a pull request from the comamnd line but this can also be easily achieved from the GitHub web interface.

### Get the app
```
gh repo clone https://github.com/jptmoore/miiifyapp.git
cd miiifyapp
```

### Fork an annotation git repo
```
gh repo fork --clone https://github.com/jptmoore/annotations.git db
```

### Install app dependencies (requires Node.js)
```
npm install
```

### Start miiify backend (requires Docker)
```
npm run backend
```

### Start demo
```
npm run serve
```

Visit http://localhost:8080/ and annotate the image by drawing a rectangle with your mouse.

![Example](doc/example.png)

### Share your edits

The db directory is the forked [annotations](https://github.com/jptmoore/annotations) repo which you can issue a Pull Request (PR) to share your contributions.

Change into the db repo and push your changes back to your remote.

```
cd db
git push origin master
```

Create a PR from your changes. You can use the defaults when prompted.
```
gh pr create
```
### Get the latest edits

Make sure you are in the directory where the repo is and clean any unstaged changes that might have been generated.
```
cd db
git reset HEAD --hard
```
Pull in the any changes from the upstream [annotations](https://github.com/jptmoore/annotations) repository.

```
git pull upstream master
```
