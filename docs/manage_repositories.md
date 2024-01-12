# ros-misc-utilities repository management

## First time release of repository:

Follow
[these](https://docs.ros.org/en/humble/How-To-Guides/Releasing/First-Time-Release.html)
instructions. Use the minor revision to prevent tag collisions. The
following convention is currently used:

- Rolling: 1.0.x
- Humble:  1.1.x
- Iron:    1.2.x
- Jazzy:   1.3.x

When it asks for the upstream repository branch, answer with the respective release branch, e.g. "humble", not "master".

## New release of existing repositories

Assuming you are in your workspace and suppose you want to create a new release of ``ffmpeg_image_transport`` for distro Humble that captures the changes in ``master``:
```bash
my_repo=ffmpeg_image_transport
distro=humble
#
cd src/${my_repo}
# make sure the master is up-to date
git checkout master && git pull
# look that every thing is committed
git status
# checkout the distro branch
git checkout ${distro} && git pull
# apply the latest changes from master to distro release branch
git merge master
# generate the changelog
catkin_generate_changelog
# edit the CHANGELOG.rst file, save it, and COMMIT(!) it
git commit -a -m "updated changelog"
# bump the package version, create tags etc
catkin_prepare_release
# push the updates to the release repository
bloom-release --rosdistro ${distro} ${my_repo}
```
Now run the same for the other distros you want to release,
e.g. ``rolling``.

