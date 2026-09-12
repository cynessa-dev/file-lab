# FILELAB

An experimental offline-first file repository system whose goal is to streamline common office works in both low and high latency areas. Additionally, its offline-first nature will allow users be able to use it even without internet connection.

## Other Documentations

- [Architecture](https://github.com/cynessa-dev/file-lab/blob/04ecda9b9b14153585ca213c082371f4b8ffa62f/ARCHITECTURE.md)

## Quick Start

### Normal Route

To get started, you can follow the normal route, if you don't want to use Docker. Open up a terminal, and follow the commands below to clone:

**NOTE: Keep the terminal open if this is your first time doing this**

```
git clone https://github.com/cynessa-dev/file-lab.git
cd file-lab/
```

then, you wanna go to the `frontend/` to download the dependencies:

```
cd frontend/
npm install
```

after that (assuming you are still on `frontend/`), you can now enter:

```
npm run dev
```

\
If nothing went wrong, go ahead and open a browser and type `localhost:5173` in the address bar to see the web app.

And that should start the dev environment for the `frontend/`. There is currently no `backend/` as it is still under development, but there will be one soon.

To turn it off, simply press `Ctrl + C`, or `Cmd + C` for Mac users, on the same terminal that `npm run dev` is running to stop it.

<br />

### Docker Route

If you want to use docker, you can follow these steps to get the dev environment up and running.

**NOTE: This guide assumes you already have Docker installed. If not, please follow the [Docker Documentation](https://docs.docker.com/get-started/get-docker/) for installation based on your Operating System.**

First, clone the repository (if you haven't already):

```
git clone https://github.com/cynessa-dev/file-lab.git
cd file-lab/
```

Then, you will notice a `docker-compose.dev.yml` file. That's the development file that uses docker compose to combine different services for the app, and it is **recommended** that you use that.

To use it, you can just enter:

```
docker compose -f docker-compose.dev.yml up --watch
```

This spins up the services that is in the `docker-compose.dev.yml` file, and does all the needed step to setup the environment for you.

The `--watch` flag allows you to modify the contents under `src/`, `package.json`, and `vite.config.ts`. Docker then sync or restart the containers for you see the changes.

After that, you can now open a browser and type in the address bar `localhost:5173` to access the app.

## Tech Stack

- Vue + TypeScript (v^3.5.40)
- Go (v1.26.8)
- PostgreSQL
- Docker (v29.8)
- Terraform (v1.16.1)
- GitHub Actions
- Google Cloud

Tech Stacks are explain in [ARCHITECTURE.md](https://github.com/cynessa-dev/file-lab/blob/04ecda9b9b14153585ca213c082371f4b8ffa62f/ARCHITECTURE.md) so make sure to check it out.

---

<div align="center">
  Made with ❤️ by Christian Mamplata
  
  mamplata.cb@gmail.com
</div>
