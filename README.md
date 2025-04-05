# test_inertial
roslaunch urdf_tutorial display.launch model:=/home/bao/k67_ws/src/bao/urdf/my_robot.urdf
rosrun gazebo_ros spawn_model -file /home/bao/NCKH/src/vehicle.urdf -urdf -model vehicle.urdf_name
Tóm tắt các thay đổi chính:

    Thêm link world.
    Thêm joint world_to_court để cố định court vào world.
    Sửa kích thước <visual> của court thành 15 8 0.01.
    Thêm thẻ <inertial> cho court và cot.
    Điều chỉnh giá trị Z trong origin của robot_to_court thành 0.05 để đặt đáy robot lên mặt sân.
    Điều chỉnh giá trị Z trong origin của cot_joint thành 1.215 (một nửa chiều dài cột) để cột đứng trên mặt sân.
    (Tùy chọn) Thêm thẻ <origin> vào visual, collision, inertial của court để đặt gốc tọa độ ở mặt trên.

Hãy thử lại với phiên bản URDF đã sửa đổi này. Việc thêm liên kết world và đảm bảo court có độ dày hợp lý cả về visual và collision là rất quan trọng.
