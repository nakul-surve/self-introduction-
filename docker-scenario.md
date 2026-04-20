1- your cantinar starts and exit immidetly, how do you debug i?

Scenario: You run docker run myapp and it stops within seconds with no error on screen.

First, run docker ps -a to see the exited container. Then run docker logs <container_id> to read the output — the app likely crashed due to a missing env variable, wrong CMD, or a startup error. Fix the issue in the Dockerfile or pass the missing env var with -e.

---

2- a contanier is runnung but your app is not accessable on the expated port. what do you check?

Scenario: Your web app container is up, but hitting localhost:3000 gives "connection refused".

Check if you published the port correctly — run docker ps and look at the PORTS column. If it's empty, you forgot -p 3000:3000 in your run command. Also verify the app inside the container is actually listening on that port, not 127.0.0.1 (which blocks external access).

---

3- how do you get inside a runnung countanier to inspact it? 

Scenario: Your app behaves unexpectedly and you want to check files, env vars, or running processes inside the container.

Run docker exec -it <container_id> /bin/sh (or /bin/bash if available). This gives you a shell inside the container. You can then use env to check env vars, ls to check files, or ps aux to see running processes.

---

4- tow contaniers wants to needs to each other but cant how do you fix it? 

Scenario: Your Node.js app container can't reach the Postgres container even though both are running.

By default, containers on separate networks can't communicate. Put both on the same custom Docker network using docker network create mynet and start each with --network mynet. Then the Node app can reach Postgres using the container name as hostname, e.g. postgres://db:5432. With Docker Compose, this is automatic

---


