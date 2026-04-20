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

5- your contanier consuming too much memory and gets killd, what do you do?

Scenario: The container keeps restarting because the OOM (Out of Memory) killer terminates it.

First confirm with docker inspect <id> — look for OOMKilled: true. Then either fix a memory leak in your app, or set a memory limit with --memory=512m to prevent it from eating the whole host. Also check if you're loading large files or caching too aggressively.

---

6- you docker image is 1.5gb, how would you reduce its size?

Scenario: A colleague built an image for a Go app and it's unnecessarily large, slowing down CI/CD pipelines.

Use a multi-stage build — compile the Go binary in a full build image, then copy only the binary into a minimal base like FROM scratch or alpine. Also: remove unnecessary packages, avoid installing build tools in the final image, and add a .dockerignore to exclude node_modules, .git, test files, etc.

---

7- every time you build docker rebulids all layers from scratch. how do you fix slow builds?

Scenario: A simple code change triggers a full reinstall of all npm packages, making builds take 3+ minutes.

This is a layer caching issue. In your Dockerfile, copy package.json and run npm install BEFORE copying your source code. Since package.json changes rarely, Docker caches the install layer. Only copy your app code after — that way only changed code layers rebuild.

---


8- you need different docker configuritions for dev and prod. how do you handel this? 

Scenario: Dev needs hot reload and debug tools, but prod should be a lean, optimized image.

Use multi-stage builds with named stages like FROM node AS dev and FROM node AS prod. You can also use two separate Compose files — docker-compose.yml as the base and docker-compose.override.yml for dev-specific settings. Build for a specific target using --target dev or --target prod.

---

9- your CI pipline fails because a new docker build brock the app how do you roll back?

Scenario: A bad image was pushed to the registry. Production is affected.

Pull the last known good image by tag — e.g. docker pull myapp:v1.2.3 — and redeploy it immediately. This is why you should never rely on the latest tag in production — always tag images with a version or git commit SHA so rollbacks are simple and reliable.

---

