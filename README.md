# AIMS AI Toolbox Demo Tool

The tool is a simple demonstration for the AIMS AI Toolbox. The tool itself executes a simple *Canny* edge detection on a provided image.

## Usage
The tool can be used as a conventional AI tool (see the [AI Toolbox](https://github.com/aims50toolbox/aitoolbox)). You can experiment with the `query.ipynb` to check the tool capabilities. Also, you can deploy the tool as a REST service. Suppose, the tool is checked out into `~/aitools/demo`, then you can deploy it into `/tmp/demo_deploy` 
```
python3 -m aitoolbox deploy ~/aitools/demo -o /tmp/demo_deploy
```

After that, go to the deploy directory and build the image:
```
cd /tmp/demo_deploy
docker compose build
docker compose up
```

Running the service, you can test it with the provided `test/example.http` file and the Visual Code REST client extension, or using 
```
cd ~/aitools
curl --data-binary @demo/assets/aitoolbox-impl.png -H "Mime-Type: image/png" -H "Content-Type: image/png" http://localhost:12345 > response.png
```
