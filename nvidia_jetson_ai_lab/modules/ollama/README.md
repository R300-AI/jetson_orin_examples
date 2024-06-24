# ollama

<details open>
<summary><b><a id="Server">Ollama Server</a></b></summary>
<br>
First, start the local Ollama server as a daemon in the background, either of these ways:

```
# models cached under jetson-containers/data
jetson-containers run --name ollama $(autotag ollama)

# models cached under your user's home directory
docker run --runtime nvidia -it -rm --network=host -v ~/ollama:/ollama -e OLLAMA_MODELS=/ollama dustynv/ollama:r36.2.0
```

You can then run the ollama [client](#ollama-client) in the same container (or a different one if desired).  The default docker run CMD of the `ollama` container is [`/start_ollama`](./start_ollama), which starts the ollama server in the background and returns control to the user. The ollama server logs are saved under your mounted `jetson-containers/data/logs` directory for monitoring them outside the containers.

Setting the `$OLLAMA_MODELS` environment variable as shown above will change where ollama downloads the models to.  By default, this is under your `jetson-containers/data/models/ollama` directory which is automatically mounted by `jetson-containers run`.  

<img src="https://github.com/R300-AI/jetson_orin_examples/blob/nvidia_jetson_AI_Lab/nvidia_jetson_ai_lab/src/gif/ollama_server.gif" width="750px"></img>

</details>

<details open>
<summary><b><a id="WebUI">Open WebUI</a></b></summary>
<br>

To run [Open WebUI](https://github.com/open-webui/open-webui) server for client browsers to connect to, use the `open-webui` container:

```
docker run -it --rm --network=host --add-host=host.docker.internal:host-gateway ghcr.io/open-webui/open-webui:main
```

You can then navigate your browser to `http://JETSON_IP:8080`, and create a fake account to login (these credentials are only stored locally)

<img src="https://github.com/R300-AI/jetson_orin_examples/blob/nvidia_jetson_AI_Lab/nvidia_jetson_ai_lab/src/gif/webui.gif" width="750px"></img></details>

Select Model

<img src="https://github.com/R300-AI/jetson_orin_examples/blob/nvidia_jetson_AI_Lab/nvidia_jetson_ai_lab/src/images/webui_choose_model.png" width="400px"></img>

<img src="https://github.com/R300-AI/jetson_orin_examples/blob/nvidia_jetson_AI_Lab/nvidia_jetson_ai_lab/src/images/ollama_webui.png" width="800px"></img>


</details>

<details open>
<summary><b><a id="build">BUILD CONTAINER</b></summary>
<br>

If you use [`autotag`](/docs/run.md#autotag) as shown above, it'll ask to build the container for you if needed.  To manually build it, first do the [system setup](/docs/setup.md), then run:
```bash
jetson-containers build ollama
```
The dependencies from above will be built into the container, and it'll be tested during.  Run it with [`--help`](/jetson_containers/build.py) for build options.
</details>

<details open>
<summary><b><a id="demo">Demo</b></summary>
<br>

<img src="https://github.com/R300-AI/jetson_orin_examples/blob/nvidia_jetson_AI_Lab/nvidia_jetson_ai_lab/src/gif/ollam_demo.gif" width="900px"></img>

</details>