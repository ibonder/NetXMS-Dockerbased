# NetXMS-Dockerbased

Modified repo of @hellofaduck with WebUI included.
Original link: https://github.com/hellofaduck/NetXMS-Docker

Automatically builds with latest available version of NetXMS. 
- Current version of NetXMS Server and WebUI in image on docker hub is 3.8.314
- If you don't have your own postgres database server (or docker image with postgres) use docker compose file from github repo to deploy a complete stack (recommended). For update netxms in stack from my docker compose file do not use ouroboros or watchtower, just recompose whole stack with docker-compose, it can save you from problem:"Can't resolve postgres hostname" wich shows up in netxms logs (i try to fix this in future relases)
- If you use only this docker container and you have your own postgres server that you additionally configure through ENV variables you feel free to update it as you want, automatically by ouroboros etc. or manually, no issues found yet in this case
- All options for startup and configuration listed in files in human-readable format, you can get it in github repository (you can use docker compose for tested examples of config)

Instruction for a complete deploy:
1) clone or download this repo to your preferred host machine
2) open your terminal app there, become root (sudo -i)
3) make sure you have docker and docker-compose installed
4) run "docker-compose up" and wait for everything to deploy
5) open your browser and type "http://NODE-IP:8080/nxmc/nxmc"
6) great, you've successfully deployed NetXMS network monitoring and management system and you won't lose your config if something, because postgres has a persistent volume!
7) * if you want to change something in images - make changes in server/webui directories, run docker build to your repo and replace image names in docker-compose file *

If anything, feel free to contact me on reddit https://www.reddit.com/user/yeahwhatchasay or via GitHub Issues segment
