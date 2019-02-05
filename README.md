## To create the skeleton:

Run `vue create project-name` then `cd` to the project folder and `yarn install electron concurrently wait-on`

Then add the following scripts to the `package.json` file:

```
"start": "concurrently 'yarn serve --port 4000' 'wait-on http://localhost:4000 && yarn electron-start'",
"electron-start": "yarn run electron ."
```

Must have an index.js in the root of the folder in which electron is run. This file must containt the starting code for the electron app (which listens to the specified port on which the vue app runs: `mainWindow.loadURL('http://localhost:4000');`)

## To run:
```
yarn start
```
