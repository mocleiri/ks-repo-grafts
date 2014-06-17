# Kuali Student Repository Grafts

The original conversion of the full kuali student repository into Git
resulted in a repository over 2.3 GB.

Github has a recommendation that the repository be less than 1GB in size and a hard limit on files being larger than 100 MB.

This project contains the grafts file that should be used to allow developers
to clone the historical repositories and have a single unified history.

## Historical Repositories

| Start Date | End Date | Github Repository |
| --- | --- | --- |
| 2008 | 2013-03-01 | [ks-2008-to-2013-01-01](https://github.com/mocleiri/ks-2008-to-2013-01-01) |
| 2013-03-01 | 2014-01-05 11:59 | [ks-2013-01-01-to-2014-01-05](https://github.com/mocleiri/ks-2013-01-01-to-2014-01-05) |
| 2014-01-05 12:00 | present | [ks-current](https://github.com/mocleiri/ks-current) |

## Instructions

Clone **ks-current** from github

```
$ git clone https://github.com/mocleiri/ks-current

$ cd ks-current

$ git remote add 2008-to-2013 https://github.com/mocleiri/ks-2008-to-2013-01-01

$ git remote add 2013-to-2014 https://github.com/mocleiri/ks-2013-01-01-to-2014-01-05

$ git fetch 2008-to-2013

(wait)

$ git fetch 2013-to-2014

(wait)

```

At this point there are three distinct git commit graphs in the repository.

You can find the commit ids like this to confirm

```
$ git log --all --max-parents=0
```

Copy the *grafts* file into your **ks-current/.git/info** directory.

Now you should see a unified graph in gitk.

