# Course git tool
Bash utility to fetch/pull/clone students git repository in a course.
Used extensivly in my Advanced C++ Courses.

## environment variables used
* `$COURSE_GIT_URL`     course git base URL
* `$COURSE_GIT_REPO`    name of repo

## Sample commands
### First time
```
mkdir cs101; cd cs101
./gitclass -o mhz-ninjas -ik cs101  hw jane cindy tao karim
```
* Create folder for course `cs101`
* Clone repos for students: jane cindy tao karim.
* Repo name is `cs101`
* full git URL is `git@${COURSE_GIT_URL}:mhz-ninjas/cs101.${STUDENT}.git`
* for jane it will be something like `git@$github.com:mhz-ninjas/cs101.jane.git

Alternatively, if we have no common prefix for user names:
```
COURSE_GIT_URL=`github.com`  ./gitclass -k "" -r hw jane joe
```
* where `-k ""` is used to specify no class name prefix.

### Pulling
Once we have cloned the repos, repeating the same command will do git pull.
```
./gitclass -r hw jane cindy tao karim
```

## Advanced Options
See `./gitclass -h` for more.
