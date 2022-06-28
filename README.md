** Build
- `source poky/oe-init-build-env`
- to build the image you need to run `bash docker.sh` from this directoty. This will build the docker image and open a bash. The current directory will be mapped as a volume
- to build the image run `bitbake core-image-minimal`
- 
** Menuconfig
- from within the docker bash run `bitbake -c menuconfig virtual/kernel`

** Clean
`bitbake bitbake -c cleanall`# ubuntu_20_yocto
