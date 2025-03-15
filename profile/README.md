# ros-misc-utilities

This page is the landing page for the ROS2 release team "ros-misc-utilities".

## Repositories/Packages

### Released to rosdistro

The following packages are indexed by rosdistro and can be installed with a package manager:
- [ffmpeg_image_transport](https://www.github.com/ros-misc-utilities/ffmpeg_image_transport/):
  a ROS2 image transport plugin for leveraging ffmpeg for hardware-accelerated image compression.

- [ffmpeg_image_transport_msgs](https://www.github.com/ros-misc-utilities/ffmpeg_image_transport_msgs/):
  messages package for [ffmpeg_image_transport](https://www.github.com/ros-misc-utilities/ffmpeg_image_transport/).

- [ffmpeg_image_transport_tools](https://www.github.com/ros-misc-utilities/ffmpeg_image_transport_tools/):
  tools for processing [ffmpeg_image_transport_msgs](https://www.github.com/ros-misc-utilities/ffmpeg_image_transport_msgs/).

- [ffmpeg_encoder_decoder](https://www.github.com/ros-misc-utilities/ffmpeg_encoder_decoder/):
  wrapper around ffmpeg/libav for video compression. This package is used by the ffmpeg_image_transport and foxglove_compressed_video_transport.

- [foxglove_compressed_video_transport](https://www.github.com/ros-misc-utilities/foxglove_compressed_video_transport/):
  a ROS2 image transport plugin for producing Foxglove CompressedVideo messages using ffmpeg.

- [apriltag_detector](https://www.github.com/ros-misc-utilities/apriltag_detector/):
  ROS2 packages to detect and visualize Apriltags with the UMich and  MIT Apriltag library.
  
- [apriltag_mit](https://www.github.com/ros-misc-utilities/apriltag_mit/):
  ROS2 vendor package containing the MIT implementation of the Apriltag library.

- [flex_sync](https://www.github.com/ros-misc-utilities/flex_sync/):
  ROS2 package similar to the standard ros message_filters package, but the number of data sources to be synced does not have to be known at compile time.

### Not released to rosdistro

The following packages have not (yet) been indexed by rosdistro and need to be compiled from source.

- [ros_build_scripts](https://github.com/ros-misc-utilities/ros_build_scripts): has some simple workflow files for continuous integration testing.



## How to manage and release repositories

[Here are more instructions](docs/manage_repositories.md) on how to manage and release the ros-misc-utilities repositories.



