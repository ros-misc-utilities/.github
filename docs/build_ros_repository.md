# How to download and build a ROS repository

## Define repository name and URL

Set the following variables to point to your repository (replace
``foo`` and ``foo_repository`` with the name and url of the repository
you want to downloads)

```bash
repo=foo
url=http://github.com/bar/foo_repository.git
```

## Create workspace (if not already there)
In ROS, all source and build files live in a workspace. In case
you don't have one, create one like this, for example in your home
directory:

```bash
mkdir -p ~/${repo}_ws/src
```

## Download the repo and install its dependencies

```bash
cd ~/${repo}_ws/src  # or wherever your workspace is
# download the repo
git clone ${url}
# download source repos that the downloaded repository depends on, if any
cd src; [ -f ${repo}/${repo}.repos ] && vcs import < ${repo}/${repo}.repos ; cd ..
# install all remaining other system and ROS dependencies via package manager
rosdep install --from-paths . --ignore-src --rosdistro=${ROS_DISTRO}
```

## Configure and build on ROS2

```bash
cd ~/${repo}_ws  # or wherever your workspace is
colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=RelWithDebInfo  # (optionally add -DCMAKE_EXPORT_COMPILE_COMMANDS=1)
```


## Configure and build on ROS1

```bash
cd ~/${repo}_ws  # or wherever your workspace is
catkin config -DCMAKE_BUILD_TYPE=RelWithDebInfo  # (optionally add -DCMAKE_EXPORT_COMPILE_COMMANDS=1)
catkin build
```
