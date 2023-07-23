# Sandbox for NewZeaLiDAR project


## Setup

1. git clone to the local host.

1. open the terminal, and go to the repository directory.

1. fill and/or modify the `.env` file referring to the `.env-example`.

1. open `docker-compose.yml` and replace path `../datastorage` in `- "../datastorage:/home/jovyan/datastorage"` to real datastorage path.

1. execute `docker-compose up --build -d`.

1. server terminal> `docker exec -it cont_lidar_run /bin/bash`

1. docker terminal> `git clone https://github.com/xandercai/NewZeaLiDAR.git`

1. docker terminal> `python NewZeaLiDAR/run.py`
