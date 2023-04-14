# capture_canon_on_linux


## Instalar dependencias 


~~~
sudo apt install ffmpeg
sudo apt-get install gphoto2
sudo apt-get install gphoto2-dev
~~~

## 

~~~
sudo modprobe v4l2loopback exclusive

sudo modprobe v4l2loopback exclusive_caps=1 max_buffer=2

sudo modprobe -r v4l2loopback 
~~~

~~~
gphoto2 --stdout --capture-movie | ffmpeg -i - -vcodec rawvideo -pix_fmt yuv420p -threads 0 -f v4l2 /dev/video2

~~~
