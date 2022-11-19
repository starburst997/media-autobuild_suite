# Notessimo's Fork

Minimal `ffmpeg.exe` to turn `.avi` into `.mp4` (1.85 MB)

Clone this repository and simply launch `media-autobuild_suite.bat` to build an exact replica of `ffmpeg.exe` that is bundled with [Notessimo](https://notessimo.net), the binaries are then available at `local64/bin-video/ffmpeg.exe`.

Includes [`x264`](https://github.com/starburst997/x264/tree/notessimo-1), [`AviSynthPlus`](https://github.com/starburst997/AviSynthPlus/tree/notessimo-1), [`l-smash`](https://github.com/starburst997/l-smash/tree/notessimo-1), [`upx`](https://github.com/starburst997/upx/tree/notessimo-1)

Currently use [`ffmpeg`](https://github.com/starburst997/FFmpeg/tree/notessimo-1) version `5.0.2` released on November 4th 2022.

GIT url points on my own fork to makes sure binary is always the same.

You can replace `ffmpeg.exe` with your own version or delete it and it will attempt to use the version installed on your computer.

A [complete archive](https://cdn.notessimo.com/source/ffmpeg.exe.source.7z) / snapshot of the source is also available if any of the downloads from the script ever becomes unavailable.

# media-autobuild_suite

Before opening an issue, check if it's an issue directly from executing the suite. This isn't Doom9, reddit, stackoverflow or any other forum for general questions about the things being compiled. This script builds them, that's all.

This source code is also mirrored in [GitLab](https://gitlab.com/RiCON/media-autobuild_suite).

Most git sources in the suite use GitHub, so if it's down, it's probably useless to run the suite at that time.

## Download

**[Click here to download latest version](https://github.com/m-ab-s/media-autobuild_suite/archive/master.zip)**

For information about the compiler environment see the wiki, there you also have a example of how to compile your own tools.

## Included Tools And Libraries

### [Information about FFmpeg external libraries](https://github.com/m-ab-s/media-autobuild_suite/wiki/ffmpeg_options.txt)

- FFmpeg (shared or static) with these libraries (all optional, but compiled by default unless said otherwise):
    - Light build:
        - amd amf encoders (built-in)
        - cuda (built-in)
        - cuda-llvm (built-in)
        - cuvid (built-in)
        - ffnvcodec (git)
        - libaom (git)
        - libdav1d (git)
        - libfdk-aac (git)
            - needs non-free license if not LGPL
        - libmp3lame (mingw-w64)
        - libopus (mingw-w64)
        - libvorbis (mingw-w64)
        - libvpx (git)
        - libx264 (git)
        - libx265 (git)
        - nvdec (built-in)
        - nvenc (built-in)
        - schannel with gmp (mingw-w64)
            - enabled by default if openssl, libtls, mbedtls or gnutls aren't enabled
            - gmp can be switched by gcrypt (mingw-w64) with --enable-gcrypt
        - sdl2 (2.0.10) (needed for ffplay)
            - enabled by default, use --disable-sdl2 if unneeded
    - Zeranoe-emulating build (in addition to Light)
        - avisynthplus (needs avisynth dll installed)
        - fontconfig (latest release)
        - only one of these TLS libs (including schannel) can be enabled at once:
            - openssl (mingw-w64)
                - preferred to gnutls and to libtls if all three are in options
                - needs non-GPL license
            - libtls (from libressl) (latest release)
                - needs non-GPL license
            - mbedtls (mingw-w64)
                - preferred to gnutls if GPLv3 license is chosen
            - gnutls (latest release)
        - libass (git)
            - by default with DirectWrite backend
            - if --enable-fontconfig, fontconfig backend included
            - with harfbuzz (latest release)
        - libbluray (git)
            - BD-J support requires installation of Java JDK
            - BD-J support after compilation probably only requires JRE (untested)
        - libfreetype (latest release)
        - libgsm (mingw-w64)
        - libmfx (git)
        - libmodplug (mingw-w64)
        - libopencore-amr(nb/wb) (mingw-w64)
        - libopenjpeg2 (mingw-w64)
        - libopenmpt (git tag)
        - librav1e (git)
        - libsnappy (mingw-w64)
        - libsoxr (git)
        - libspeex (mingw-w64)
        - libsrt (git)
        - libsvtav1 (git)
        - libtheora (mingw-w64)
        - libtwolame (mingw-w64)
        - libvidstab (git snapshot)
        - libvmaf (git)
        - libvo-amrwbenc (0.1.3)
        - libwebp (git)
        - libxml2 (mingw-w64)
        - libxvid (1.3.7)
        - libzimg (git)
    - Full build (in addition to Zeranoe)
        - chromaprint (mingw-w64)
        - cuda filters (needs CUDA SDK installed)
            - needs non-free license
        - decklink (12.3)
            - needs non-free license
        - frei0r (git)
        - ladspa (mingw-w64)
        - libaribb24 (git)
        - libbs2b (3.1.0)
        - libcaca (mingw-w64)
        - libcdio (mingw-w64)
        - libcodec2 (git)
        - libdavs2 (git)
        - libflite (git)
        - libfribidi (latest release)
        - libglslang (git)
        - libgme (git snapshot)
        - libilbc (git snapshot)
        - libjxl (git)
        - libkvazaar (git)
        - libmysofa (git)
            - needed for sofalizer filter
        - libnpp (needs CUDA SDK installed)
            - needs non-free license
        - libopenh264 (official binaries)
        - librist (git)
        - librtmp (git)
        - librubberband (git snapshot)
        - libssh (broken)
        - libsvthevc (git) (using non-upstream patch)
        - libsvtvp9 (git) (using non-upstream patch)
        - libtesseract (git)
        - libuavs3d (git)
        - libxavs (git)
        - libxavs2 (git)
        - libzmq (mingw-w64)
        - libzvbi (0.2.35)
        - openal (git)
        - opencl (from system)
        - opengl (from system)
        - vapoursynth (R57)
        - vulkan (git)

- other tools
    - aom (git)
    - bmx (git)
    - curl (latest release) with WinSSL/LibreSSL/OpenSSL/mbedTLS/GnuTLS backend
    - cyanrip (git)
    - dav1d (git)
    - dssim (git)
    - exhale (git)
    - faac (1.30)
    - fdk-aac (git)
    - ffmbc (git) (unsupported)
    - flac (git)
    - haisrt tools (git)
    - jo (git)
    - jpeg-xl tools (git)
    - jq (git)
    - kvazaar (git)
    - lame (3.100)
    - libaacs (git) (shared)
    - libavif (git) with following encoders/decoders:
        - rav1e (enc only)
        - aom (enc/dec)
        - dav1d (dec only)
    - libbdplus (git) (shared)
    - mediainfo cli (git)
    - mp4box (git)
    - mplayer (svn) (unsupported)
    - mpv (git) including in addition to ffmpeg libs:
        - Base build (ffmpegChoice=2 or 3)
            - ANGLE Headers (git)
                - requires ANGLE shared libraries from somewhere else (i.e. Chrome, Firefox) for gpu-context=angle support
            - lcms2 (mingw-w64)
            - libass (git)
            - libbluray (git)
                - BD-J support requires installation of Java JDK
                - BD-J support after compilation probably only requires JRE (untested)
            - luajit (mingw-w64)
            - mujs (git)
            - rubberband (git snapshot)
            - uchardet (mingw-w64)
            - vulkan, shaderc, spirv-cross, libplacebo (git)
            - vapoursynth (R52)
        - Full build (ffmpegChoice=4)
            - dvdnav (git)
            - libarchive (mingw-w64)
            - shared libmpv
            - openal (git)
    - opus-tools (git)
    - rav1e (git)
    - ripgrep (git)
    - rtmpdump (git)
    - sox (14.4.2)
    - speex (git)
    - svt-hevc (git)
    - svt-av1 (git)
    - tesseract (git)
    - uvg266 (git)
    - vvenc & vvdec (git)
    - vorbis-tools (git snapshot)
    - vpx (VP8 and VP9 8, 10 and 12 bit) (git)
    - vvc tools (git)
    - webp tools (git)
    - x264 (8 and 10 bit, with l-smash [mp4 output], lavf and ffms2) (git)
    - x265 (8, 10 and 12 bit) (git)
    - xvc (git) (unsupported)
    - xvid (1.3.7)

--------

## Requirements

--------

- Windows 64-bits (tested with Win10 64-bits)
  - 32-bit hosts are no longer supported.
- NTFS drive
- 13GB+ disk space for a full 32 and 64-bit build, 8GB+ for 64-bit
- 4GB+ RAM
- At least Powershell 4, Powershell core is not supported at this time
  - Powershell 5.1 can be downloaded [here](https://www.microsoft.com/en-us/download/details.aspx?id=54616)

--------

## Information

--------

This tool is inspired by the very nice, linux cross-compiling tool from Roger Pack (rdp):
<https://github.com/rdp/ffmpeg-windows-build-helpers>

It is based on msys2 and tested under Windows 7, 8.1. and 10.
<http://sourceforge.net/projects/msys2/>

I use some jscript parts from nu774:
<https://github.com/nu774/fdkaac_autobuild>

Thanks to all of them!

This Windows Batchscript setups a Mingw-w64/GCC compiler environment for building ffmpeg and other media tools under Windows.
After building the environment it retrieves and compiles all tools. All tools get static compiled, no external .dlls needed (with some optional exceptions)

How to use it:

- Download the file, and extract it to your target folder or `git clone` the project. Compilers and tools will get installed there. Please make sure you use a folder without space characters. A good place might be: c:\mabs
- Double click the media-autobuild_suite.bat file
- Select if you want to compile for Windows 32-bit, 64-bit or both
- Select if you want to compile non-free tools like "fdk aac"
- Select the numbers of CPU (cores) you want to use
- Wait a little bit, and hopefully after a while you'll find all your "*.exe" tools under local32\bin-(audio|global|video) or local64\bin-(audio|global|video)

The Script writes a ini-file, so you only need to make these choices the first time what you want to build.

The script doesn't build any registry key or system variables, when you don't need it any more you can delete the folder and your system will be clean.
Building everything from scratch takes about ~3 hours depending on what is enabled.

Check [forcing-recompilations](./doc/forcing-recompilations.md) to check how you can force a rebuild of all libs/binaries.

To save a bit of space you can delete, after compiling, all source folders (except the folders with a "-git" or "-svn" on end) in /build. There's an option in the .bat for the script to remove these folders automatically.

Have fun!

## Troubleshooting

--------

If there's some error during compilation follow these steps:

1. Make sure you're using the latest version of this suite by downloading the [latest version](https://github.com/m-ab-s/media-autobuild_suite/archive/master.zip) and replacing all files with the new ones;
2. If you know which part it's crashing on, delete that project's folder in /build and run the script again (ex: if x264 is failing, try deleting x264-git folder in /build);
3. If it still doesn't work, [create an issue](https://github.com/m-ab-s/media-autobuild_suite/issues/new) and paste the URL to `logs.zip` that the script gives or attach the file yourself to the issue page.
4. If the problem isn't reproducible by the contributors of the suite, it's probably a problem on your side. Delete /msys64, /local32 and /local64 if they exist. /build is usually safe to keep and saves time;
5. If the problem is reproducible, it could be a problem with the package itself or the contributors will find a way to probably make it work.
6. If you compile with `--enable-libnpp` and/or `--enable-cuda-nvcc`, see [Notes about CUDA SDK](#notes-about-cuda-sdk)

## What The Individual Files Do

--------

`media-autobuild_suite.bat`

- This file sets up the msys2 system and the compiler environment. For normal use you only have to start this file. Every time you start this batch file it runs through the process, but after the first time it only checks some variables and run updates to the MinGW environment. After that it only compiles the tools that get updates from git.

`/build/media-autobuild_suite.ini`

- This file get generated after the first start and saves the settings that you have selected. Before the next run you can edit it.

`/build/media-suite_compile.sh`

- This is the compiling script, it builds all the libs and tools we want, like ffmpeg; mplayer; etc. You can also inspect it and see how to compile your own tools. Normally you can copy the code and paste it in the mintty shell (except `make -j $cpuCount`, here you need to put your cpu count). You don't need to start this script, it's called by the batch script.

`/build/media-suite_update.sh`

- This script runs every time you run the batch file. It checks for updates from msys2's pacman etc.

`/build/media-suite_helper.sh`

- This script contains helper functions used by compile and update that can also be `source`'d by the user if desired.

`/build/ffmpeg_options.txt` & `/build/mpv_options.txt`

- If you select the option to choose your own FFmpeg/mpv optional libraries, this file will contain options that get sent to FFmpeg/mpv's configure script before compiling. Edit this file as you wish to get a smaller FFmpeg/mpv without features you don't need or with additional features not compiled by default, if supported.

## Optional User Files

--------

`/local32|64/etc/custom_profile` & `$HOME/custom_build_options`

- Put here any general/platform tweaks that you need for _your_ specific environment. See `/local32|64/etc/profile2.local` for example usage.

## Custom Patches

--------

Using custom patches is not officially supported, if you do use custom patches, do not expect much support from this suite. Either go to the patch's author or to a forum for help

- It is assumed that you, the reader, have enough knowledge of bash specifically in order to understand some basic terminology. If not, please look up what you do not know.
- It is highly recommended to look through the [compile script](build/media-suite_compile.sh) for the exact package you want to modify and cross-reference the functions with the [helper script](build/media-suite_compile.sh) to see what is actually being done.
- Although it is recommended to use the functions provided in the helper script, there is nothing stopping you from using the actual commands.

--------

- To use a custom patch, within the build folder, create a script with the filename: `<repository's name>_extra.sh`.
  - For ffmpeg, the folder name is ffmpeg-git, but the repository's name would be ffmpeg: `ffmpeg_extra.sh`.
  - For game-music-emu, the folder name is game-music-emu-0.6.2, but the repository's name would be game-music-emu: `game-music-emu_extra.sh`
  - Case-sensitivity applies, so for the folder name SVT-VP9-git (repo name SVT-VP9), the script filename would be: `SVT-VP9_extra.sh`

- The commands will run in the cloned/unzipped folder unless otherwise stated. (flac_extra.sh would run commands within flac-git)

To reference the cloned folder itself (`flac-git` `ffmpeg-git`) you can use the variable `${REPO_DIR}`.
To reference the generated build folder, you would need to use `${REPO_DIR}/build-${bits}` to reference the build-64bit folder for 64 bit builds or build-32bit folder for 32 bit builds.

- For some packages, the build folder may be slightly different (`build-shared-${bits}` for shared ffmpeg or `build-light-${bits}` for light build, etc. Try to compile at least once to see what folders are generated or look through the [compile script](build/media-suite_compile.sh))

If you are building for both 32 and 64-bit, you can gate certain commands using `if [ "$bits"="64bits" ]; then <command>; fi` to only run them when building for 64 bits.\
Be careful with certain packages due to their unique build process (x265, x264, and some others) so make sure to check the compile script

Example Script: `/build/aom_extra.sh` for `aom-git`

``` bash
#!/bin/bash

# Don't automatically run cmake || configure
touch do_not_reconfigure

# Commands to run before running cmake
_pre_cmake(){
    # Installs libwebp
    do_pacman_install libwebp
    # Downloads the patch and then applies the patch
    do_patch "https://gist.githubusercontent.com/1480c1/9fa9292afedadcea2b3a3e067e96dca2/raw/50a3ed39543d3cf21160f9ad38df45d9843d8dc5/0001-Example-patch-for-learning-purpose.patch"
    # Change directory to the build folder
    cd_safe "build-${bits}"
    # Run cmake with custom options. This will override the previous cmake commands.
    # $LOCALDESTDIR refers to local64 or local32
    cmake .. -G"Ninja" -DCMAKE_INSTALL_PREFIX="$LOCALDESTDIR" \
        -DCMAKE_BUILD_TYPE=Release -DCMAKE_C_COMPILER=clang \
        -DBUILD_SHARED_LIBS=off -DENABLE_TOOLS=off
}

_post_cmake(){
# post cmake and post configure will be unavailable due to "touch do_not_reconfigure"
# as the do_not_reconfigure flag will skip the post commands.
}

# Commands to run before building using ninja
_pre_ninja(){
    # Change directory to the build folder (Absolute path or relative to aom-git)
    cd_safe "build-${bits}"
    # applies a local patch (Absolute or relative to aom-git)
    do_patch "My-Custom-Patches/test-diff-files.diff"
    # run a custom ninja command.
    ninja aom_version_check
    # Not necessary, but just for readability sake
    cd_safe ..
}

```

Example Script: `/build/ffmpeg_extra.sh` for `ffmpeg-git`

``` bash
#!/bin/bash

# Force to the suite to think the package has updates to recompile.
# Alternatively, you can use "touch recompile" for a similar effect.
touch custom_updated

_pre_configure(){
    #
    # Apply a patch from ffmpeg's patchwork site.
    do_patch "https://patchwork.ffmpeg.org/patch/12563/mbox/" am
    #
    # Apply a local patch inside the directory where is "ffmpeg_extra.sh"
    patch -p1 -i "$LOCALBUILDDIR/ffmpeg-0001-my_patch.patch"
    #
    # Add extra configure options to ffmpeg (ffmpeg specific)
    # If you want to add something to ffmpeg not within the suite already
    # you will need to install it yourself, either through pacman
    # or compiling from source.
    FFMPEG_OPTS+=(--enable-libsvthevc)
    #
}

_post_make(){
    # Don't run configure again.
    touch "$(get_first_subdir -f)/do_not_reconfigure"
    # Don't clean the build folder on each successive run.
    # This is for if you want to keep the current build folder as is and just recompile only.
    touch "$(get_first_subdir -f)/do_not_clean"
}
```

For a list of possible directive, look under `unset_extra_script` in [media-suite_helper.sh](build/media-suite_helper.sh).
Beware as they may change in the future.

## Notes about CUDA SDK

--------

### This is for cuda-nvcc and libnpp, not for NVENC, it is built with ffmpeg by default

For `--enable-cuda-nvcc` and `--enable-libnpp` to work, you need NVIDIA's [CUDA SDK](https://developer.nvidia.com/cuda-toolkit) installed with `CUDA_PATH` variable to be set system-wide (Usually set by default on CUDA SDK install) and VS2017 or better installed which should come with `vswhere.exe`.\
If for some reason `CUDA_PATH` isn't set and/or `vswhere.exe` isn't installed, you need to export the `CUDA_PATH` variable path using the above mentioned user files and manually export the correct `PATH` including the absolute `cygpath` converted path to MSVC's `cl.exe`.

### You do not need to do the following if you installed the SDK with the default locations etc and you have 8.3 short paths enabled or if you installed to a directory without any spaces

If you did not understand any of the words above, assume the best and hope the compilation will succeed the first time, else try reinstalling the SDK and MSVC to a path without any spaces.

You will only need to be worried if running the following command in the mintty terminal produces a path with a space or if you have 8.3 short paths disabled.

```bash
cygpath -sm "$CUDA_PATH"
```

If running the above command produces a path with a space, you will need to either disable cuda/npp stuff or reinstall your cuda sdk to a path without spaces.

### Nothing should be disabled manually when installing CUDA SDK as disabling random things can cause the compilation to fail

For example, if you need to manually set the `CUDA_PATH` and include in the `PATH` the binaries for MSVC `cl.exe` and `nvcc.exe`, add this bit of bash script inside a text file in `/local64/etc/custom_profile`:

```bash
# adapt these to your environment
_cuda_basepath="C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA"
_cuda_version=10.0

_msvc_basepath="C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Tools\MSVC"
_msvc_version=14.15.26726
_msvc_hostarch=x64
_msvc_targetarch=x64

# you shouldn't need to change these unless your environment is weird or you know what you're doing
export CUDA_PATH=$(cygpath -sm "${_cuda_basepath}")/${_cuda_version}
export PATH=$PATH:$(dirname "$(cygpath -u "\\${_msvc_basepath}\\${_msvc_version}\bin\Host\\${_msvc_hostarch}\\${_msvc_targetarch}\cl.exe")")
export PATH=$PATH:$CUDA_PATH/bin
```
