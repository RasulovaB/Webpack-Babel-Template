# Webpack-Babel-Template
Reusable webpack package

**Using Babel**
1. Install `Node.js` (and `npm`) on the computer 

2. Use `npm init` to create a `package.json` file in the project directory

3. Use `npm` to install babel/core & babel/cli packages 

  
    `npm install @babel/core @babel/cli --save -dev`
    
    - to save in developer dependencies and list as dependencies inside the `package.json` file
    
4. Install the babel presets (env)

   `npm install @babel/preset -env --save -dev`
  
    - this preset will allow us to use all of the latest JS features 
    
  <hr>
  
**Using Webpack**

  
 **Create `webpack.config.js` file**

In this file we specify how we want webpack to work (webpack control center)

Example: 

 ``` 
 const path = require('path');
 module.exports = {
      entry: './src/index.js',
      output: {
          path: path.resolve(__dirname, 'dist/assets'),
          filename: 'bundle.js'
      }
      };
 ```
 
 It's going to outline things like where our source files are located and where they should be bundled
 
 *Next steps*
 
 - To install webpack cli:
   `npm isntall webpack webpack-cli --save-dev`
   
 - To install webpack dev server
   `npm isntall webpack-dev-server@3.2.1`
   
    - add to `webpack.config.js` file 
    
    
    ```
    devServer: {
      contentBase: path.resolve(__dirname, 'dist'),
      publicPath: '/assets/'   
    }
    
    ```
 - To install babel loader
   ` npm install babel-loader --save -dev `
   
 - To configure this loader in webpack create module property
   
   - add to `webpack.config.js` file 
   
   ``` 
     module: {
        rules: [{
            test: /\.js$/,
            exclude: /node_modules/,
            use: {
                loader: 'babel-loader',
                options: {
                    presets: ['@babel/preset-env']
                }
            }
        }]
    }
    
   ```
   
   
   
   
   
   
