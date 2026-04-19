1- what is docker and why do we use it?

Docker is a tool that packages your app along with everything it needs (code, libraries, settings) into a container. This ensures the app runs the same way on any machine — no more "it works on my laptop" problems.

---

2- what is the difference between docker image and a docker containr?

An image is like a blueprint or recipe — it's a read-only template stored on disk. A container is a running instance of that image — like a cake baked from the recipe. You can run many containers from one image.

---

3- what is dockerfile?

A Dockerfile is a plain text file with step-by-step instructions to build a Docker image. Each line (like FROM, RUN, COPY, CMD) adds a layer to the image. Think of it as the "recipe" for your image.

---

4- what dose docker build, docker run, and docker push do?

docker build reads your Dockerfile and creates an image. docker run takes that image and starts a container from it. docker push uploads your image to a registry like Docker Hub so others can use it.

---

5- what is dockerhub?

Docker Hub is a public registry (like GitHub, but for Docker images) where you can store and share images. You can pull official images like nginx or postgres from there, or push your own.

---

6- what is a multi stage docker build and why it is use full?

Multi-stage build lets you use multiple FROM statements in one Dockerfile. You build your app in one stage (with all build tools) and copy only the final binary into a slim second stage. This keeps production images small and secure — no build tools left behind.

7- what is docker compose? 

Docker Compose lets you define and run multi-container apps using a single YAML file (docker-compose.yml). Instead of running 5 docker run commands manually, one docker compose up starts your whole stack — app, database, cache, etc.

8- what is the difference between CMD and ENTRY POINT in docker file?

ENTRYPOINT sets the main command that always runs when the container starts. CMD provides default arguments to that command that can be overridden at runtime. Think of ENTRYPOINT as the "what to run" and CMD as the "default arguments".

9- what are the docker layers and why they matters?

Every instruction in a Dockerfile creates a layer (a cached snapshot). Docker reuses unchanged layers when rebuilding, which makes builds faster. This is why you should put frequently changing lines (like COPY . .) near the bottom of your Dockerfile.

10- what is the difference between docker stop and docker kill? 

docker stop sends a SIGTERM signal, giving the container a chance to shut down gracefully (save state, close connections). docker kill sends SIGKILL, which terminates the container immediately with no cleanup — use it only when the container is stuck.

---

