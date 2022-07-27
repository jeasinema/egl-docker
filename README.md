# egl-docker

A customized docker for headless GPU rendering without host-side configuration. Inspiried by the [orginal repo](https://github.com/ehfd/docker-nvidia-egl-desktop) by [Seungmin Kim](https://github.com/ehfd).

Please note that [MineRL](https://github.com/minerllabs/minerl) is also installed for testing purposes. You may remove that part for good.

## Build

```bash
git clone https://github.com/jeasinema/egl-docker && cd egl-docker
docker build . -t <docker_name>
```
 
## Run

```bash
docker run --gpus all -it <docker_name>:latest /bin/bash
```

Inside the docker container, you may verify if GPU rending is working use the following command
```bash
vglrun /opt/VirtualGL/bin/glxspheres64
```
If you can something like `OpenGL Renderer: NVIDIA GeForce RTX 3090/PCIe/SSE2` in the output, GPU rendering is working.

To run your own application with GPU rendering, prepand commands with `vglrun`.
```bash
vglrun <your_command>
```



