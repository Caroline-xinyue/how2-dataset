# Reproducible Pipeline for 300h

- Make sure you are working in a Python 3.x environment (preferably >= 3.6) and you
are able to install additional dependencies with `pip`.

- The reproducible pipeline requires the following Python packages to be available.
You can install these packages simply by running `pip install -r requirements.txt` command
in the root of the cloned repository.

```
 - youtube-dl>=2018.11.07
 - webvtt-py==0.4.2
 - tqdm
 - requests
```

- You will also need the `sha1sum` and `parallel` utilities:

```
# Ubuntu (sha1sum should already be installed)
apt install parallel

# Mac OS X (You need homebrew)
brew install coreutils parallel
```

- Finally, run the installation script `scripts/install.sh` from within the
  `reproduce/300h` folder:

```
$ scripts/install.sh <# of parallel jobs for subtitle fetching>
```

If you encounter any errors regarding the download of the subtitle files, please
try to upgrade `youtube-dl` to an even more recent version before reporting the issue.

**NOTE:** You still need to pass through the `Option 1` in order to download pre-extracted feature files.

## Fetching videos

If you also want to download the video files, modify `scripts/install.sh` and
remove the `--skip-download` argument given to `youtube-dl`.

## Issues as of October 2019

Unfortunately, some of the video files are removed from Youtube, which avoids downloading their subtitle files. This is the current list that you should be seeing once you launch the script:

```
Missing 20 subtitles/videos for train:
  1l6MC-9BQa0
  1mWIOvyqfUI
  1tIYY7yjdxI
  2N20JDU14CQ
  2Qn2pn6ReWE
  3D2JV01YRcE
  5T6dxlSxTEc
  5yZGdmZ9Hrk
  BtgP4ZHwmdw
  CNlh1WKGyWo
  CXbQug3h_wc
  DNA_UjrbSyM
  EBcv0a2jznE
  ESXuXDOmvDM
  ElqzSc-zW2M
  _aB_yyHjlRs
  aPJ6ILkkvc0
  bsLj1m4k020
  cyemyhihk2s
  dMb2kWTL1zE
Missing 1 subtitles/videos for dev5:
  G23G21G49dk
```
