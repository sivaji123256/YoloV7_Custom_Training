# yolov7
yolov7 for cusom dataset
# 1) clone the repo in colab or in local system
   ! git clone  https://github.com/adithya70/yolov7.git
# 2) change directory to yolov7 parent folder.
   * In the parent folder goto data folder and access custom.yaml file and add the required path to the train dataset and test dateset and change other parametrs as requited
   * run the following command to install required packages 
     * !pip install -r requirements.txt
     * !sudo apt install -y zip htop screen libgl1-mesa-glx
   
   * In the parent folder add required yolov7 pretrained weights.pt files
# 3) Training custom dataset
   * Use the following command to start training on custom dataset. 
     * !python train.py --weights yolov7.pt --data "data/custom.yaml" --workers 4 --batch-size 4 --img 416 --cfg cfg/training/yolov7.yaml --name yolov7 --hyp     data/hyp.scratch.p5.yaml --epochs 5     
   
# 4) For evaluation 
    * Run the following command 
    !python tools/eval.py --data dataset.yaml  --weights runs/train/exp/weights/best_ckpt.pt --device 0
# 5) For inference run the following command
    !python detect.py --weights runs/train/yolov7/weights/best.pt --source "path to your testing image"
