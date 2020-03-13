# 概要
画像のピクセル領域を元に物体の把持位置を検出するパッケージです。ただし、現段階では物体のクラスタ重心をそのまま把持位置として出力するだけです。  
また、このパッケージを使う際は、メッセージ型依存のため別パッケージのe_object_recognizerをmakeする必要があります。  

# 実行方法  
    $ roslaunch realsense_camera r200_nodelet_rgbd.launch  
    $ rosrun e_grasping_position_detector grasping_position_detector  
realsense_cameraは別パッケージ  

# 入出力  
1.把持位置検出  
入力 /object/image_range e_object_recognizer/ImageRange  
出力 /object/xyz_centroid geometry_msgs/Point  
画像のピクセル領域（top,bottom,left,rightがそれぞれ何ピクセル目か）を受け取り、その物体の把持位置（クラスタ重心）を返す。  

# その他
  
