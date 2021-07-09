# node-git
A `node:16-alpine:latest` image with git preinstalled to support installing from git repositories

## On Docker Hub
[https://hub.docker.com/repository/docker/rightisleft/node-git](https://hub.docker.com/repository/docker/rightisleft/node-git)

## Problem Solved
The default node alpine docker images do not contain git binaries. This breaks git based support.

```
npm ERR! code 127
npm ERR! command failed
npm ERR! command git ls-remote ssh://git@github.com/rightisleft/axios.git
npm ERR! sh: git: not found

npm ERR! A complete log of this run can be found in:
npm ERR!     /root/.npm/_logs/2021-07-09T16_45_55_614Z-debug.log
```
## package.json and git?

Yes! You can host your own node modules using a public git repo instead of npmjs.org. This can help simplify your CI/CD workflow.
## Installing the npm packages from git

* Navigate to the npm package GitHub repository.

* Copy the https URL available on the browser tab and run the npm install command like this.

* npm install https://github.com/rightisleft/axios
This installs the forked axios package from the GitHub repository and it adds the following dependency to your package.json file.

```
"axios": "git+https://github.com/rightisleft/axios",
```

You can set the version of an npm package from the GitHub repository from git tag or commit hash

*Git Tag*
```
npm install https://github.com/rightisleft/axios#v0.15.1
```

 *Git Hash*
```
npm install https://github.com/rightisleft/axios#3f8b128
```