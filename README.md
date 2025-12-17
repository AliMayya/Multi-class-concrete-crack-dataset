# Multi-class-concrete-crack-dataset

## Owners
Nizar Faisal Alkayem  
Ali Mahmoud Mayya 

## URL:
https://drive.google.com/file/d/1lg3oAt9PRh3BKyoMuPR4XCbiybkwb___/view?usp=sharing

## Crack types: 
scaling (403), spalling (415), simple crack (392), severe crack (395), and the normal case (424)
 

## Python code to show classes and distribution
import os

dataset_path = '/MultiClassConcreteCrack'

#List all directories (classes) in the dataset path
class_folders = [f.name for f in os.scandir(dataset_path) if f.is_dir()]

print("Image counts per class:")
for class_name in class_folders:
    class_path = os.path.join(dataset_path, class_name)
    image_count = 0
    # Count image files in each class folder
    for filename in os.listdir(class_path):
        if filename.lower().endswith(('.png', '.jpg', '.jpeg', '.gif', '.bmp')):
            image_count += 1
    print(f"  {class_name}: {image_count} images")
## Python code to show classes and distribution
#Specify the root directory and the subfolders
root_dir = '/MultiClassConcreteCrack'
subfolders = ["normal", "scaling", "severe crack", "simple crack","spalling"]

#Display four example images from each class
for subfolder in subfolders:
    class_dir = os.path.join(root_dir, subfolder)
    image_files = [f for f in os.listdir(class_dir) if f.endswith(('.png', '.jpg', '.jpeg'))]

    fig, axs = plt.subplots(1, 4, figsize=(20, 5))
    fig.suptitle(subfolder, fontsize=20)

    for i in range(4):
        img = Image.open(os.path.join(class_dir, image_files[i]))
        axs[i].imshow(img)
        axs[i].axis('off')

    plt.show()
