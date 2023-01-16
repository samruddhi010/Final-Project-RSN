# Final-Project-RSN
The ORB_SLAM3 folder contains the code we used, with the adjustments needed to run ORB SLAM. 
ORB SLAM was run without ROS on one machine on EuRoC and segments of TUMVI data, then compared to provided groundtruths. 

For this, files edited include:

    evaluation/evaluate_ate_scale.py 
    Eliminated plotted error bars between our runs and groundtruths so trajectory comparison was easier to see. 
    
    all .cc files in Examples_old folders
    Replaced '#ifdef COMPILEDWITHC11' with '#ifdef COMPILEDWITHC14' to fix compiler errors with monotonic clock. Other dependencies 
    required use of c++ 14 rather than c++ 11. 

    Tuned and added necessary parameters to .yaml files for relevant datasets to eliminate ''missing required input' errors. 
    This was also done to the KITTI .yaml files, but we were ultimately unable to get KITTI running properly for other reasons. 

ORB_SLAM3 was run with ROS on a different machine on the NUance car 'car_IR_RGB_lidar dataset'. 
The group was unable to get ORB_SLAM with ROS and ORB_SLAM without ROS running on the same machine. 
To upload all code to one GitLab account, the custom .yaml files necessary to run the NUance data have been added to this repository. 
Since there was no single code base with everything working, these files have been added to the main ORB_SLAM3 folder for ease of access. 
    custom_params_mono.yaml is used to run monocular camera.
    custom params_s.yaml is used to run stereo cameras. 
    custom params_si.yaml is used to run stereo cameras with integrated IMU. 

To run in a functioning ORB_SLAM3 ROS environment, these files should be added to ORB_SLAM3/Examples/ROS/<appropriate folder name (mono, stereo, or stereoi)>
