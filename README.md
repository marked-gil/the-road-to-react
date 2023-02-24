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

### **React JSX**
* **JSX** (Javascript XML) - powerfully combines HTML & Javascript; a syntax extension to Javascript.

    These days, the underlying build tools can be configured to acknowledge JSX in a `.js` file.

    Tools like Vite embrace the .jsx extension though, because it makes it more explicit for developers.

### **Linting with ESLint**
1. Install Vite's plugin to integrate ESLint  
    > `npm install vite-plugin-eslint --save-dev`   
2. Integrate the plugin in the project's configuration  
    *vite.config.jsx*
    <pre>
    import { defineConfig } from 'vite';
    import react from '@vitejs/plugin-react';
    <b>import eslint from 'vite-plugin-eslint'</b>;
    
    // https://vitejs.dev/config/
    export default defineConfig({
        <b>plugins: [react(), eslint()]</b>,
    })
    </pre>
3. Install ESLint dependency   
    > `npm install eslint --save-dev`   
4. Install one of ESLint's many standardized linting configurations for a React project 
    > `npm install eslint-config-react-app --save-dev`  
5. Create an EsLint configuration file to define our linting rules  
    > `touch .eslintrc` 
6. Tell ESLint to use the previously installed standardized set of rules from the eslint-config-react-app dependency (Although, it is possible to define your own rules in this file)   
    *.eslintrc*
    <pre>
    {
        "extends": [
            "react-app"
        ]
    }
    </pre>  

### Lists in React
`map()` method - used to transform a list of items into JSX by returning JSX for each item. 
* Every React element in a list should have a `key` assigned to it.
* The `key` is an HTML attribute and should be a stable identifier.
* As a last resort, you can use the `index` of the item in the list if the list does not change its order in any way.

### **React Props** 
Important about **Props**:  
* It's not allowed to change them (they should be treated as an immutable data structure)
* Only used to pass info down the component hierarchy.
* Can only be passed from a parent to a child component & not vice versa.