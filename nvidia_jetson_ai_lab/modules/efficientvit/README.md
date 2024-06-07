# efficientvit

<details open>
<summary><b><a id="run">RUN CONTAINER</a></b></summary>
<br>

To start the container, you can use [`jetson-containers run`](/nvidia_jetson_ai_lab/docs/run.md) and `autotag`, or manually put together a [`docker run`](https://docs.docker.com/engine/reference/commandline/run/) command:
```bash
# automatically pull or build a compatible container image
jetson-containers run $(autotag efficientvit)

# or explicitly specify one of the container images above
jetson-containers run dustynv/efficientvit:r35.3.1

# or if using 'docker run' (specify image and mounts/ect)
sudo docker run --runtime nvidia -it --rm --network=host dustynv/efficientvit:r35.3.1
```
</details>

<details open>
<summary><b><a id="example">EfficientViT Benchmark Example</a></b></summary>
<br>
This guide will walk you through running a benchmark script for EfficientViT-L2-SAM inside a container to verify its output.

### Download the l2.pt Model

First, you need to download the `l2.pt` model file:

```sh
mkdir -p /data/models/efficientvit/sam/

cd /data/models/efficientvit/sam/

wget https://huggingface.co/han-cai/efficientvit-sam/resolve/main/l2.pt
```

### Run the Benchmark Script

1. Navigate to the `/opt/efficientvit` directory inside the container:

    ```sh
    cd /opt/efficientvit
    ```

2. Run the benchmark script:

    ```sh
    python3 ./benchmark.py
    ```

At the end of the run, you should see a summary similar to the following:

```
AVERAGE of 2 runs:
  encoder --- 0.062 sec
  latency --- 0.083 sec
Memory consumption :  3419.68 MB
```

### Check the Output Result

The output image file (from the last inference result) is stored as `/data/benchmarks/efficientvit_sam_demo.png`.

This file is stored in the `/data/` directory mounted from the Docker host. Therefore, you can go back to your host machine and check the `jetson-containers/data/benchmark/` directory.

You should find the output like this:

![demo_image](https://github.com/R300-AI/jetson_orin_examples/blob/nvidia_jetson_AI_Lab/nvidia_jetson_ai_lab/src/images/efficientvit_sam_demo.png)

</details>

<details open>
<summary><b><a id="build">BUILD CONTAINER</b></summary>
<br>

If you use `autotag` as shown above, it'll ask to build the container for you if needed.  To manually build it, first do the [system setup](/nvidia_jetson_ai_lab/docs/setup.md), then run:
```bash
jetson-containers build efficientvit
```
The dependencies from above will be built into the container, and it'll be tested during.  Run it with [`--help`](/jetson_containers/build.py) for build options.
</details>

<details open>
<summary><b><a id="Demo">Demo</b></summary>
<br>
<img src="https://github.com/R300-AI/jetson_orin_examples/blob/nvidia_jetson_AI_Lab/nvidia_jetson_ai_lab/src/gif/efficientvit.gif?raw=true" width="750px"></img>
</details>
