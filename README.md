# slam_karto
Original Repo : <https://github.com/ros-perception/slam_karto>  
Offline mapping node is added.
  
## Nodes
### slam_karto
Online SLAM node from original repository.

### slam_karto_offline
Offline SLAM node.

#### 1. Published Topics
map ([nav_msgs/OccupancyGrid](http://docs.ros.org/melodic/api/nav_msgs/html/msg/OccupancyGrid.html))  
Map data is published only when "publish_map" service is called.
  
map_metadata ([nav_msgs/MapMetaData](http://docs.ros.org/melodic/api/nav_msgs/html/msg/MapMetaData.html))  

visualization_marker_array ([visualization_msgs/MarkerArray](http://docs.ros.org/melodic/api/visualization_msgs/html/msg/MarkerArray.html))  
This is also published only when "publish_map" service is called.


#### 2. Services
The following services are added.  
  
publish_map ([std_srvs/Empty](http://docs.ros.org/jade/api/std_srvs/html/srv/Empty.html))  
Request to publish map data.

#### 3. Parameters
The following parameters are added.  
  
~bag_filename (string, default: "")  
File path of rosbag file.  
  
~scan_topic (string, default: "")  
Topic name of laser scan data.  
  
~start_time_sec (double, default: 0.0)  
Start mapping from this time. [sec]  
  
~laser_range_threshold (double, default: 80.0)  
Threshold of the laser scan ranges. [m]  