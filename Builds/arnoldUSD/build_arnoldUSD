#Step 0: Setup Environment
        visual studio 2019
        NASM ?
        CMake ?
        python 3.9
            pip install PyOpenGL
            pip install PySide2


#Step 1: Get latest arnold release from arnold-usd

download the source code from the link or clone the repository
https://github.com/Autodesk/arnold-usd/releases/tag/Arnold-7.1.3.0


#Step 2: Get latest arnoldSDK

download the SDK from the arnold website
https://arnoldrenderer.com/download/


#Step 3: (optional)Compile a USD version compatible with arnold-usd(step1)

You will need a usd build with the arnold specification, if you dont have one follow build_USD guide,
You can check what version is suported for arnold in the changelogs.

#Step 4: Build arnoldUSD

cmake -G "Visual Studio 16 2019"
-DCMAKE_INSTALL_PREFIX=		output path
-DARNOLD_LOCATION= 			arnoldSDK path
-DUSD_INCLUDE_DIR= 			usdBuild(step3)\include"
-DUSD_LIBRARY_DIR= 			usdBuild(step3)\lib"
-DBUILD_SCHEMAS=			OFF
-DTBB_FOUND=				ON
-DTBB_INCLUDE_DIRS=			usdBuild(step3)\include"
-DTBB_LIBRARIES=			usdBuild(step3)\lib\tbb.lib"
-DBUILD_USE_CUSTOM_BOOST=	ON
-DBoost_INCLUDE_DIRS=		usdBuild(step3)\include\boost-1_70"
-DBoost_LIBRARIES= 			usdBuild(step3)\lib\boost_python39-vc142-mt-x64-1_70.lib"
-DBUILD_USE_PYTHON3=		ON
-DPython3_ROOT_DIR= 		python install path
addAtTheEnd					arnold-usd repo (step1)

example:
"C:\Program Files\CMake\bin\cmake.exe" ^ -G "Visual Studio 16 2019" ^ -DCMAKE_INSTALL_PREFIX="G:\USD_builds\my_builds\USD_arnold_sandbox" ^ -DARNOLD_LOCATION="C:\Program Files\Autodesk\Arnold\Arnold-7.1.3.0-windows" ^ -DUSD_INCLUDE_DIR="G:\USD_builds\my_builds\21_08\USD_complete\include" ^ -DUSD_LIBRARY_DIR="G:\USD_builds\my_builds\21_08\USD_complete\lib" ^ -DBUILD_SCHEMAS=OFF ^ -DTBB_FOUND=ON ^ -DTBB_INCLUDE_DIRS="G:\USD_builds\my_builds\21_08\USD_complete\include" ^ -DTBB_LIBRARIES="G:\USD_builds\my_builds\21_08\USD_complete\lib\tbb.lib" ^ -DBUILD_USE_CUSTOM_BOOST=ON ^ -DBoost_INCLUDE_DIRS="G:\USD_builds\my_builds\21_08\USD_complete\include\boost-1_70" ^ -DBoost_LIBRARIES="G:\USD_builds\my_builds\21_08\USD_complete\lib\boost_python39-vc142-mt-x64-1_70.lib" ^ -DBUILD_USE_PYTHON3=ON ^ -DPython3_ROOT_DIR="C:\Users\LucasMorante\AppData\Local\Programs\Python\Python39" ^ "C:\Users\LucasMorante\Desktop\_Repos\arnold-usd"

"C:\Program Files\CMake\bin\cmake.exe" --build . --config Release --target install

#Step 5: Check on usdView

add PXR_PLUGINPATH_NAME environment variable pointing to <outputPath>/plugin"

Use an environment like this on usdView to check

@ECHO OFF

SET "USD_INSTALL_ROOT=G:\USD_builds\my_builds\21_08\USD_complete"
SET "ARNOLD_USD_ROOT=G:\USD_builds\my_builds\USD_arnold_sandbox"
SET "PYTHON=%USERPROFILE%\AppData\Local\Programs\Python\Python39"

SET "PATH=%USD_INSTALL_ROOT%\bin;%USD_INSTALL_ROOT%\lib"
SET "PATH=%PATH%;%PYTHON%\Scripts;%PYTHON%;C:\Program Files\Autodesk\Arnold\Arnold-7.1.3.0-windows\bin"
SET "PYTHONPATH=%USD_INSTALL_ROOT%\lib\python"

SET "PXR_PLUGINPATH_NAME=%ARNOLD_USD_ROOT%/plugin"
SET "LD_LIBRARY_PATH=%LD_LIBRARY_PATH%;%USD_INSTALL_ROOT%\lib"

usdview.cmd G:/USD_builds/USDbuild_nvidia/share/usd/tutorials/convertingLayerFormats/Sphere.usd
PAUSE

