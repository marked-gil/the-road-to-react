# The Road to React 
## 2023 Edition

### **Verify node & npm version**s
> `node --version`    
`npm --version`

### **Setup React Project with VITE**
> `npm create vite@latest hackter-stories -- --template react`  
`cd hacker-stories`     
`npm install`   
`npm run dev`

### **npm scripts**
All project-specific commands are in the `package.json` under `scripts` property.
> `npm run dev` - runs the application locally for the browser (local development)  
`npm run build` - builds the application for production (creates *dist/* folder)     
`npm run preview` - to run production-ready build on local machine for testing purposes (run after `npm run build`)

### **Meet React Component**
**Rule of thumb:**  
"If a variable does not need anything from within a component's body, then define it outside of the component which avoid re-defining it on every function call.
<pre>const title = 'React';

function App() {  
    return (  
        ... 
    )   
}</pre>

THe function of a component runs every time a component is displayed in the browser - on initial rendering of component, and whenever the component updates