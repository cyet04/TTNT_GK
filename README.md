# TTNT_GK
Tạo thư mục chứa ảnh (Dataset) theo đường dẫn : Dataset/FaceData/raw như ảnh dưới 
![image](https://github.com/user-attachments/assets/a772c74c-7ade-450f-ad0c-5fe1c55934b6)

Import các thư viện cần thiết : pip install -r requirements.txt 

Lấy dataset : 
python capture.py

Với chỗ ảnh đã sưu tầm bên trên, có thể là ảnh cả người, bây giờ chúng ta sẽ cắt riêng khuôn mặt ra để train:
python src/align_dataset_mtcnn.py  Dataset/FaceData/raw Dataset/FaceData/processed --image_size 160 --margin 32  --random_order --gpu_memory_fraction 0.25

 Train model: 
 python src/classifier.py TRAIN Dataset/FaceData/processed Models/20180402-114759.pb Models/facemodel.pkl --batch_size 1000

 Nhận diện: 
 python src/face_rec_cam.py
