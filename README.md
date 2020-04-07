# opencvjs

> This is demo project to tell you how to build opencv.js with extra modules like aruco, alphamat, bgsegm and others in the opencv_contrib

1. Make a folder to store all the project
```
mkdir opencv-system
```

2. Git clone all the projects which you need
```
git clone https://github.com/NearZXH/opencvjs.git
git clone https://github.com/opencv/opencv.git
git clone https://github.com/opencv/opencv_contrib.git
```

After that, your folder should like this:
```
drwxr-xr-x   3 user  staff    96B Apr  7 20:31 opencv
drwxr-xr-x  13 user  staff   416B Apr  7 20:35 opencv_contrib
drwxr-xr-x   4 user  staff   128B Apr  7 20:31 opencvjs
```

3. Go to the opencvjs
```
cd opencvjs
```

Here is two soft link to the folder outside
```
lrwxrwxrwx 1 user user   9 Apr  7 20:29 opencv -> ../opencv
lrwxrwxrwx 1 user user  17 Apr  7 20:29 opencv_contrib -> ../opencv_contrib
```

The `docker-compose.yml` file is the environment you need to build opencv.js.You should have the `docker` and `docker-compose` command

4. Go to opencv build_js.py folder
```
cd ../opencv/platforms/js
vim build_js.py
```

5. Add `"-DOPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules",` in the `cmd` list of the function `get_cmake_cmd`.

Now you have add the extra_modules of opencv_contrib

6. Add "js" parameter in ocv_define_module of `opencv_contrib/modules/aruco/CMakeLists.txt`

7. Build
```
cd opencvjs
docker-compose up
```

8. After build, you will finde the `opencv.js` in the `opencv/build/bin/opencv.js`

