DeltaPatcher [![Codacy Badge](https://app.codacy.com/project/badge/Grade/bdfed52f118c4199ad0d828520f29b61)](https://www.codacy.com/gh/marco-calautti/DeltaPatcher/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=marco-calautti/DeltaPatcher&amp;utm_campaign=Badge_Grade)
============

Delta Patcher is yet another frontend to the
xdelta3 decoder/encoder created by Joshua
McDonald. Delta patcher is able to make and
apply patches. But... why making another frontend?
All the frontends I've seen don't support some
options of the encoder/decoder at all, like
compression level for encoding and checksum
checking for decoding/encoding. Also, they are
all written in .NET (0_0). So, this tool was
designed to be selfcontained (as of now, only
for Windows). It's written in C++ using
wxWidgets for the GUI components and all the
needed libraries are static linked to the EXE.
All you need is to place the xdelta.exe file
in the same directory of this tool (no more
.NET Framework required).
Last, but not the least, Delta Patcher is
GPL2'd and cross-platform: it runs fine on
Windows and Linux and should compile on MacOS
too.

# How to build

## Windows

- Install CMake and Visual Studio Community 2022 with the Desktop C++ Development tools (including the WindowsSDK package).
- git clone --recurse-submodules https://github.com/marco-calautti/DeltaPatcher.git
- mkdir build
- cd build
- cmake -G "Visual Studio 17 2022" -DwxBUILD_SHARED=OFF -DwxBUILD_USE_STATIC_RUNTIME=ON -DCMAKE_BUILD_TYPE=Release ..

- Open the solution file created in the build directory.
- Select Release as the build configuration and press F6.

Executable should be found in build/app/Release/

## Linux

- First install dependencies:
    - Ubuntu: sudo apt install build-essential cmake git libgtk-3-dev xdelta3
    - Fedora: sudo dnf install g++ make cmake git gtk3-devel xdelta3

- git clone --recurse-submodules https://github.com/marco-calautti/DeltaPatcher.git
- mkdir build && cd build
- cmake -DwxBUILD_SHARED=OFF -DCMAKE_BUILD_TYPE=Release ..
- make (use -j flag to speed up compilation)

The final binary should be found in build/app/

