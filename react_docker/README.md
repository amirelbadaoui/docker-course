# 📦 How to Use Docker | Learning Notes 🚀

This document contains my notes and key takeaways from the [Learn Docker in 1 Hour](https://www.youtube.com/watch?v=GFgJkfScVNU&ab_channel=JavaScriptMastery) video.

---

## 📌 React Docker Demo
- I ran npm create vite@latest react-docker to create this folder and chose React and TS
- Create a new file called Dockerfile in the react_docker folder
- I had to copy the Dockerfile from the repo provided in the video description and then he goes into depth explaining the commands
- Reference for explanantion -> (25:40)
- You can create a .dockerignore which functions similarly to .gitignore
- Put node_modules/ in your .dockerignore because we really don't need it on github or docker or anywhere
- Docker will use our package.json and package-lock.json and will rebuild node_modeles/ when it needs it
- Make sure you are in react_docker and we can build it by running docker build -t react-docker .
- Now type: docker run react-docker
- It will seem to be running on localhost:5173 
- It will not show up on your local machine even though we did EXPOSE 5173
- EXPOSE does only one job and that is to tell docker that the container should listen to that exposed port in runtime
- We know on which port the container will listen to and so does Docker but the host (our machine) is missing that info
- Containers run in isolated environments and by default they don't expose their ports to the host machine or anyone else which means that even if a process inside of a container is listening on a specific port, it is not accessible outside of the container
- To make our host machine aware of that, we have to do port mapping
- So we run: docker run -p 5173:5173 react-docker
- The first 5173 is the host port (your computer) and the second 5173 is the container port (inside Docker)
- but SAME ISSUE AGAIN??
- All is well, it's vite, notice how it says Network: use --host to expose
- We have to expose that port for vite too
- We then go to the package.json and in scripts for the dev script, we make "vite" into "vite --host"
- If you want Docker to automatically build images, that will be later in the video

---










<br>

# Auto-Generated stuff is below (ignore)

# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default tseslint.config({
  extends: [
    // Remove ...tseslint.configs.recommended and replace with this
    ...tseslint.configs.recommendedTypeChecked,
    // Alternatively, use this for stricter rules
    ...tseslint.configs.strictTypeChecked,
    // Optionally, add this for stylistic rules
    ...tseslint.configs.stylisticTypeChecked,
  ],
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config({
  plugins: {
    // Add the react-x and react-dom plugins
    'react-x': reactX,
    'react-dom': reactDom,
  },
  rules: {
    // other rules...
    // Enable its recommended typescript rules
    ...reactX.configs['recommended-typescript'].rules,
    ...reactDom.configs.recommended.rules,
  },
})
```
