# Create React App on Heroku
Create React apps with no build configuration.
This quick start guide will have you running a React app on Heroku in no time.

This guide uses @mars' Create React App Buildpack for Heroku. [Check out the readme]([create-react-app-buildpack/README.md at master · mars/create-react-app-buildpack · GitHub](https://github.com/mars/create-react-app-buildpack/blob/master/README.md)) for full configuration information.

This setup assumes knowledge of the Create React App and that you've already installed & setup Create React App.

## Jump into your terminal...
_Note: if you haven't done so already, initiate a Git repository in your working directory:_
```
git init
```

1. Create a new Heroku app for our React app to live on:
```
heroku create
```

2. Add @mars' excellent Create React App Buildpack to your app:
```
heroku buildpacks:set mars/create-react-app
```

3. Make sure everything is checked into Git:
```
git add .
git commit -m "First commit"
```

4. Push to Heroku:
```
git push heroku master
```

```
...
remote: -----> Compressing...
remote:        Done: 1.5M
remote: -----> Launching...
remote:        Released v1
remote:        https://react-test-am.herokuapp.com/ deployed to Heroku
remote:
remote: Verifying deploy... done.
```

5. Your React app is running on Heroku. Let's check it out:
```
heroku open
```



#heroku/spa