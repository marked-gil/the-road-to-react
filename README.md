# The Road to React 
## 2023 Edition

### Verify node & npm versions
> `node --version`    
`npm --version`

### Setup React Project with **Vite**
> `npm create vite@latest hackter-stories -- --template react`  
`cd hacker-stories`     
`npm install`   
`npm run dev`

### npm scripts
All project-specific commands are in the `package.json` under `scripts` property.
> `npm run dev` - runs the application locally for the browser (local development)  
`npm run build` - builds the application for production (creates *dist/* folder)     
`npm run preview` - to run production-ready build on local machine for testing purposes (run after `npm run build`)