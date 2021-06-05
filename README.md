<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white"/> <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=PyTorch&logoColor=white"/> <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=OpenCV&logoColor=white"/> <img src="https://img.shields.io/badge/Numpy-013243?style=flat-square&logo=Numpy&logoColor=white"/> <img src="https://img.shields.io/badge/GoogleColab-F9AB00?style=flat-square&logo=GoogleColab&logoColor=white"/> <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=Git&logoColor=white"/>  <img src="https://img.shields.io/badge/PyCharm-000000?style=flat-square&logo=PyCharm&logoColor=white"/> <img src="https://img.shields.io/badge/Ubuntu-E95420?style=flat-square&logo=Ubuntu&logoColor=white"/><img src="https://img.shields.io/badge/macOS-000000?style=flat-square&logo=macOS&logoColor=white"/>

# Converting 2D Single Image into 3D Model
### 2D Single Image to 3D Model using the PIFu algorithm. 

We utilized the PIFu algorithm(Saito et al. 2019) to create a 3D model of a sagittal mouse brain with a single 2D image as an input. The sagittal mouse brain image and binary masks were obtained from the source from Iqbal et al(2019).  

<br>

<img width="916" alt="3d_1" src="https://user-images.githubusercontent.com/45449025/120881597-45a13780-c60d-11eb-8fd8-c4ec50c0d01c.png">  

<img width="916" alt="3d_2" src="https://user-images.githubusercontent.com/45449025/120881608-55208080-c60d-11eb-8b37-d78f35c699a2.png">  

<img width="916" alt="3d_3" src="https://user-images.githubusercontent.com/45449025/120881615-6073ac00-c60d-11eb-9fba-56d4df382aaf.png">  

<img width="916" alt="3d_4" src="https://user-images.githubusercontent.com/45449025/120881619-69fd1400-c60d-11eb-9a65-1f9e5d885972.png">  

### Code

```
git clone https://github.com/shunsukesaito/PIFu.git
```
```
cd /content/PIFu
```
```
!sh ./scripts/download_trained_model.sh
```
```
!sh ./scripts/test.sh
```
```
!pip install 'git+https://github.com/facebookresearch/pytorch3d.git@stable'
```
```
from lib.colab_util import *
obj_path = '/content/PIFu/results/pifu_demo/result_mousebrain.obj'
video_path = '/content/PIFu/results/pifu_demo/result_mousebrain.mp4'
video_display_path = '/content/PIFu/results/pifu_demo/result_mousebrain_display.mp4'

renderer = set_renderer()
generate_video_from_obj(obj_path, video_path, renderer)

!ffmpeg -i $video_path -vcodec libx264 $video_display_path -y -loglevel quiet
video(video_display_path)
```

## For more detail : 
#### *https://youtu.be/Aa9cgU9t-58*

<img width="400" alt="Screen Shot 2021-06-05 at 3 02 16 PM" src="https://user-images.githubusercontent.com/45449025/120881854-0bd13080-c60f-11eb-9c06-4c583af739f3.png">
