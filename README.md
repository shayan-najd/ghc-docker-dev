# A docker container for hacking on GHC

To use (in Linux),

0. Set `uid` and `gid` in [the Docker file](https://github.com/shayan-najd/ghc-docker-dev/blob/master/Dockerfile#L76)

1. Build the image:
     ```shell
     sudo docker build -t ghc-dev .
     ```

2. Load the image:
     ```shell
     ./Connect.sh
     ```

You are now ready to compile GHC!
You can edit Haskell files using Emacs GUI running inside the Docker image.
There is one final setup step to run once you have the image up:

    arc install-certificate

This places a .arcrc file (which is git ignored) in your repo
arc is a tool to interface with phabricator, the main ghc development tool.
When you have a patch ready, run:
 
    arc diff

Look here on how to kick off your first build:
https://ghc.haskell.org/trac/ghc/wiki/Building/Hacking
