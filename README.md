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

```
cd db
git log
```

```
commit b2d69045d1ff69128bb4b818f9ea9b60ec4a89f4 (HEAD -> master, upstream/master, origin/master, origin/HEAD)
Author: miiify.rocks <irmin@openmirage.org>
Date:   Sat Jan 8 17:24:43 2022 +0000

    POST /demo/collection/9684d9ee-fc86-470d-9223-9a6cf3d0e2a2

commit f3de7862831291aa3ea7f2e9d8bb6ba44975c2e1
Author: miiify.rocks <irmin@openmirage.org>
Date:   Sat Jan 8 17:24:43 2022 +0000

    POST /demo/main/modified

commit 97e841196c7f2dfe0b202d1316075efc2927429a
Author: miiify.rocks <irmin@openmirage.org>
Date:   Sat Jan 8 17:24:19 2022 +0000

    POST /demo/main
```