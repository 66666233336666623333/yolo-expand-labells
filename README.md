# yolo-expand-labells
python脚本，适用于yolo系，当数据不足时进行扩充，自动翻转图片和标注信息，在学校里打比赛很好用。/ This Python script is suitable for the YOLO series and is useful for augmenting data when there is insufficient data. It automatically flips images and annotation information, making it very useful for competitions in school.

确保你已经有了图片和对应的标注信息！！！
MAKE SURE u already have picture and its labell.

简体中文(Sim Chinese):
这段代码是一个用于数据增强的Python脚本，专门用于处理图像及其对应的标注文件（假设标注文件是以某种格式存储的文本文件，如YOLO格式）。它可以对图片执行不同的转换操作，包括旋转（顺时针旋转0度、90度、180度、270度）和翻转（水平翻转、垂直翻转），同时更新相应的标注文件以匹配图像的新位置。这可以帮助提高机器学习模型的泛化能力，尤其是在图像识别和对象检测任务中。

使用前的准备：
确保Python环境已安装Pillow库（PIL）用于图像处理。
准备两个目录：一个包含原始图像（.jpg文件），另一个包含对应的标注文件（.txt文件）。标注文件格式应为YOLO格式（每行包含一个对象的类别和位置信息）。
安装好glob模块用于文件路径匹配。

使用步骤：
设置路径和参数：
输入标注文件目录路径（txtpath）。
输入图像文件目录路径（jpgpath）。
输入希望生成的数据增强副本数量（num_change）。

执行脚本：
脚本会检查标注文件和图像文件数量是否匹配。如果数量不一致，脚本会终止并提示错误。
如果数量匹配，脚本将对每个图像和其对应的标注文件执行随机选择的转换操作，包括旋转和翻转。
转换后的图像和更新后的标注文件将保存在原始目录下的copies子目录中。

注意事项：
确保classes.txt文件不在标注文件目录中，因为脚本会计算目录中.txt文件的数量。
生成的图像和标注文件的命名格式为原始文件名后追加序号（例如，原文件image.jpg和image.txt，转换后的文件可能为image_1.jpg和image_1.txt）。
脚本目前没有实现在图像上绘制文本的功能（相关代码被注释掉了）。注释掉的部分的作用为：在新生成的图片的左上角显示翻转的信息（该图片翻转类型，是0 90 180 270 垂直翻转 水平翻转中的一个）

示例代码调用：
在使用此脚本之前，你需要设置txtpath和jpgpath变量为你的标注文件和图像文件的路径，然后根据需要设置num_change变量。之后，运行脚本将自动处理所有文件，并在指定目录下创建增强的数据副本。

不想写用法（懒），用法来自chatgpt，已经很详细了。
大一写的代码，又臭又长，轻喷。尽管如此，打工训赛电赛这些不用浪费时间一个个标数据了。


English(英语）:
This script is a Python tool for data augmentation, specifically designed for images and their corresponding annotation files (assuming these annotation files are stored in a text format, such as the YOLO format). It performs various transformations on the images, including rotations (clockwise 0, 90, 180, 270 degrees) and flips (horizontal and vertical), and updates the corresponding annotation files to match the new positions of the images. This can help improve the generalization ability of machine learning models, especially for image recognition and object detection tasks.

Preparations Before Use:
Ensure your Python environment has the Pillow library (PIL) installed for image processing.
Prepare two directories: one containing the original images (.jpg files) and another containing the corresponding annotation files (.txt files). The format of the annotation files should be the YOLO format (each line contains class and position information for one object).
Have the glob module installed for file path matching.

Steps for Use:
Set Paths and Parameters:
Enter the path for the annotation files directory (txtpath).
Enter the path for the images files directory (jpgpath).
Input the desired number of data augmentation copies to generate (num_change).

Execute the Script:
The script checks if the number of annotation files matches the number of image files. If they do not match, the script will terminate and display an error message.
If the numbers match, the script will perform a randomly selected transformation operation on each image and its corresponding annotation file, including rotations and flips.
The transformed images and updated annotation files will be saved in a copies subdirectory under the original directory.

Important Notes:
Ensure the classes.txt file is not located in the annotation file directory, as the script counts the number of .txt files in the directory.
The naming format for the generated images and annotation files appends a sequence number to the original filename (for example, the original files image.jpg and image.txt might have their transformed counterparts named image_1.jpg and image_1.txt).
The script currently does not implement the functionality to draw text on images (the relevant code is commented out).The purpose of the commented-out section is to display information about the flip in the top left corner of the newly generated image, indicating the type of flip (one of 0, 90, 180, 270 degrees rotation, vertical flip, or horizontal flip).

Sample Code Invocation:
Before using this script, you need to set the txtpath and jpgpath variables to the paths of your annotation files and image files, respectively, and then set the num_change variable as required. After running the script, it will automatically process all files and create augmented data copies in the specified directories.

Translated by ChatGPT
