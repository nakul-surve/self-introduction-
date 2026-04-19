1- what is docker and why do we use it?

Docker is a tool that packages your app along with everything it needs (code, libraries, settings) into a container. This ensures the app runs the same way on any machine — no more "it works on my laptop" problems.

---

2- what is the difference between docker image and a docker containr?

An image is like a blueprint or recipe — it's a read-only template stored on disk. A container is a running instance of that image — like a cake baked from the recipe. You can run many containers from one image.

---

3- what is dockerfile?

A Dockerfile is a plain text file with step-by-step instructions to build a Docker image. Each line (like FROM, RUN, COPY, CMD) adds a layer to the image. Think of it as the "recipe" for your image.

---

