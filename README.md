# miiifyapp

Simple demo Vue.js app which uses [Miiify](https://github.com/nationalarchives/miiify) to store annotations to git.

### Get the app (uses [GitHub CLI](https://github.com/cli/cli))
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