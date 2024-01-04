#    MetaUniverse_DynaDetectSLAM

运行命令：

yolo端：
python detect_speedup_send_socket.py --source /home/why/yoloorb/online/orb2+yolov5/04/image_0 --weights ./weights/yolov5s.pt --conf 0.5 --save-txt

ORB SLAM2端：
./Examples/Stereo/stereo_kitti Vocabulary/ORBvoc.txt Examples/Stereo/test.yaml ./04

import端：
(yolov5) why@why:~/yoloorb/online/orb2+yolov5/server$ python import.py 
















#添加了python-c++通信:yolo和orb的tracking线程并行,orb在i5 cpu运行需要0.0282526一帧,所以yolo只要在0.02s内即可
因此可以使用yolov5s+imgsize224-320-416; yolov5l+imgsize224; yolov5m+imgsize224
打开两个终端,分别运行:



终端1:进入到/ORB_SLAM2_AddSemantic/yolov5_RemoveDynamic:
(python detect_speedup_send.py +path to afterchanged dataset + weights ./weights/yolov5s.pt --conf 0.4 --save-txt --img-size 224)


python detect_speedup_send.py --source /home/why/yoloorb/online/orb2+yolov5/dataset/tum_fr3_walking_xyz_afterchange/rgb/ --weights ./weights/yolov5s.pt --conf 0.4 --save-txt --img-size 224

双目命令：
python detect_speedup_send.py --source /home/why/yoloorb/online/orb2+yolov5/01/image_0 --weights ./weights/yolov5s.pt --conf 0.4 --save-txt --img-size 224



终端2:进入到/ORB_SLAM2_AddSemantic:
(./Examples/RGB-D/rgbd_tum Vocabulary/ORBvoc.txt Examples/RGB-D/TUM3.yaml + path to dataset + path to associatefile)


./Examples/RGB-D/rgbd_tum Vocabulary/ORBvoc.txt Examples/RGB-D/TUM3.yaml ./dataset/rgbd_dataset_freiburg3_walking_xyz ./dataset/rgbd_dataset_freiburg3_walking_xyz/associate.txt


双目命令：
./Examples/Stereo/stereo_kitti Vocabulary/ORBvoc.txt Examples/Stereo/KITTI00-02.yaml ./01

