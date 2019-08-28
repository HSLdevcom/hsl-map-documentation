# Instructions

Image is made using draw.io, the source xml file can be imported and modified using their online tool.

## Data flow and depending services

![Karttatuotanto data flow and depending services](karttatuotanto-flow.png)

## Karttatuotanto Docker Swarm services

![Karttatuotanto docker services](docker-services.png)
Generated with [docker-compose-viz](https://github.com/pmsipilot/docker-compose-viz)

Considering the current working directory is where your `docker-compose.yml` file is located:

```
docker run --rm -it --name dcv -v $(pwd):/input pmsipilot/docker-compose-viz render -m image docker-compose.yml
```

This will generate the `docker-compose.png` file in the current working directory.
