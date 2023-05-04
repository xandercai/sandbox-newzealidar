# Sandbox for New ZeaLiDAR with Dask and Jupyter environment


## Setup

1. git clone to the local host.

1. open the terminal, and go to the repository directory.

1. fill the `.env` file referring to the `.env.example`.

1. open `docker-compose.yml` and replace path `../datastorage` in `- "../datastorage:/home/jovyan/datastorage"` to real datastorage path.

1. execute `docker-compose up --build`.

1. copy the Jupyter link and open it on a web browser.

