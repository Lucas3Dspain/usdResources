"""
usage: build_usd.py [-h] [-n] [-v | -q] [-j JOBS] [--build BUILD] [--build-args [BUILD_ARGS ...]] [--force FORCE_BUILD] [--force-all] [--generator GENERATOR] [--toolset TOOLSET] [--src SRC] [--inst INST] [--build-shared | --build-monolithic] [--debug] [--tests | --no-tests] [--examples | --no-examples]
                    [--tutorials | --no-tutorials] [--tools | --no-tools] [--docs | --no-docs] [--python | --no-python] [--prefer-safety-over-speed | --prefer-speed-over-safety] [--imaging | --usd-imaging | --no-imaging] [--ptex | --no-ptex] [--openvdb | --no-openvdb] [--usdview | --no-usdview]
                    [--embree | --no-embree] [--prman | --no-prman] [--prman-location PRMAN_LOCATION] [--openimageio | --no-openimageio] [--opencolorio | --no-opencolorio] [--alembic | --no-alembic] [--hdf5 | --no-hdf5] [--draco | --no-draco] [--draco-location DRACO_LOCATION]
                    [--materialx | --no-materialx]
                    install_dir

C:\Users\LucasMorante\AppData\Local\Programs\Python\Python39\python.exe c:/Users/LucasMorante/Desktop/_Repos/USD/build_scripts/build_usd.py -h

C:\Users\LucasMorante\AppData\Local\Programs\Python\Python39\python.exe c:/Users/LucasMorante/Desktop/_Repos/USD/build_scripts/build_usd.py "c:/Users/LucasMorante/Desktop/_Repos/USD/final/USD"

C:\Users\LucasMorante\AppData\Local\Programs\Python\Python39\python.exe --generator Visual Studio 14 2015 Win64 c:/Users/LucasMorante/Desktop/_Repos/USD/build_scripts/build_usd.py "c:/Users/LucasMorante/Desktop/_Repos/USD/final/USD"

C:\Users\LucasMorante\AppData\Local\Programs\Python\Python39\python.exe c:/Users/LucasMorante/Desktop/_Repos/USD/build_scripts/build_usd.py "c:/Users/LucasMorante/Desktop/_Repos/USD/final/USD" --generator "MinGW Makefiles"

C:\Users\LucasMorante\AppData\Local\Programs\Python\Python39\python.exe c:/Users/LucasMorante/Desktop/_Repos/USD/build_scripts/build_usd.py "c:/USD" --generator  "Visual Studio 16 2019"

002_Fullest:
C:\Users\LucasMorante\AppData\Local\Programs\Python\Python39\python.exe c:/Users/LucasMorante/Desktop/_Repos/USD/build_scripts/build_usd.py "c:/USD" --generator  "Visual Studio 16 2019" --ptex --embree --alembic --hdf5 --openimageio --opencolorio --openvdb --tests --docs --draco --draco-location "C:\Users\LucasMorante\Desktop\_Repos\USD\plugins\draco-master" --materialx

C:\Users\LucasMorante\AppData\Local\Programs\Python\Python39\python.exe c:/Users/LucasMorante/Desktop/_Repos/USD/build_scripts/build_usd.py "c:/USD" --generator  "Visual Studio 16 2019" --ptex --embree --alembic --hdf5 --openimageio --opencolorio --openvdb

Compact:
C:\Users\LucasMorante\AppData\Local\Programs\Python\Python39\python.exe c:/Users/LucasMorante/Desktop/_Repos/USD/build_scripts/build_usd.py "C:/Users/LucasMorante/Desktop/_Repos/USD/final/USD_compact" --generator  "Visual Studio 16 2019" --no-ptex --no-embree --no-openimageio --no-opencolorio --no-openvdb --no-tests --no-docs --no-draco --no-materialx --no-examples --no-tutorials --no-tools --build-monolithic --alembic --hdf5

"""

DEBUGGING
Step 0: Setup Environment
        visual studio 2019
        NASM ? have NASM 2.13+ or YASM in your PATH
        CMake ? 
        python 3.9
            pip install PyOpenGL
            pip install PySide2

Step 1: Clone pixarUSD repo to folder
        https://github.com/PixarAnimationStudios/USD
        ../desktop/Repos/USD

Step 1.5(optional): Clone draco repo to folder
        https://github.com/google/draco
        ../desktop/Repos/USD

Step 2: Test python Environment
        C:\Users\LucasMorante\AppData\Local\Programs\Python\Python39\python.exe c:/Users/LucasMorante/Desktop/_Repos/USD/build_scripts/build_usd.py -h

Step 3: Build USD
        (run from visual Studio 2019)
        > Complete build
        C:\Users\LucasMorante\AppData\Local\Programs\Python\Python39\python.exe c:/Users/LucasMorante/Desktop/_Repos/USD/build_scripts/build_usd.py "C:/Users/LucasMorante/Desktop/_Repos/USD/final/USD_complete" --generator  "Visual Studio 16 2019" --ptex --embree --alembic --hdf5 --openimageio --opencolorio --openvdb --draco --draco-location "C:\Users\LucasMorante\Desktop\_Repos\draco" --materialx

        > Simplified build
        C:\Users\LucasMorante\AppData\Local\Programs\Python\Python39\python.exe c:/Users/LucasMorante/Desktop/_Repos/USD/build_scripts/build_usd.py "C:/Users/LucasMorante/Desktop/_Repos/USD/final/USD_compact" --generator  "Visual Studio 16 2019" --no-ptex --no-embree --no-openimageio --no-opencolorio --no-openvdb --no-tests --no-docs --no-draco --no-materialx --no-examples --no-tutorials --no-tools --build-monolithic --alembic --hdf5
