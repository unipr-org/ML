# ML
ML - Machine Learning presso l'Università degli Studi di Parma (6 CFU).

# Development Environment with Jupyter Notebook on Docker

This project sets up a development environment using [Jupyter Notebook](https://jupyter.org) on Docker. The container is based on `jupyter/minimal-notebook` image, and, has some useful packages (check `REQUIREMENTS`), allowing you to develop quantum programs locally and execute them inside the container.

## Prerequisites

Make sure you have the following tools installed on your system:

-   [Docker](https://docs.docker.com/get-docker/)
-   [Docker Compose](https://docs.docker.com/compose/install/)

## Build the Docker container

To build the Docker image and set up the container without running it immediately, use the following command:

> MacOS users may have to use the command `docker-compose`.

```bash
docker compose up --build --no-start
```

> This command will create the container but will **not** start it automatically.

### Start and stop the container

Once the build is complete, you can start the container using:

```bash
docker compose up -d
```

> This command will start the container in the background, and share sessions with the host on port `8888`.

When you're done, you can stop the running container with:

```bash
docker compose stop
```

To completely remove the container (but keep the image), you can run:

```bash
docker compose down
```

> This will stop and remove the container and the associated network. All notebooks and data won't be lost because they are stored in the shared folder (`src/`).

## Usage

To use the installed environment, you can access the Jupiter Notebook server by opening the following URL in your web browser:

```
http://localhost:8888
```

### VScode integration

If you are using VScode, you can install the [Jupiter extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) to edit `.ipynb` files, without interacting with the web browser interface.

Then, you can change the Jupiter kernel setting `localhost:8888` as the new one. This allows you to execute the Jupiter file locally.


## Personal directory

If you wish use some notebooks please create a directory named `personal` inside `src/`.
This folder will be automatically shared with the container and will not be tracked by git.