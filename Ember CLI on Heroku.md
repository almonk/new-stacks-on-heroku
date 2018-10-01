# Ember CLI on Heroku
A framework for ambitious web developers.
This quick start guide will have you running Ember CLI on Heroku in no time.

This setup assumes knowledge of the Heroku CLI and that you've already installed & setup an Ember CLI site.

## Jump into your terminal...
1. Create a new Heroku app for our Ember site to live on:
```
heroku create
```

2. Build your Ember site locally:
```
ember build
```
/Note: By default the Ember `.gitignore` file is setup to ignore `dist`. Make sure you remove this line so it gets checked in.

3. Add the Heroku Static Buildpack to your app. This will serve the contents of the `/dist` directory:
```
heroku buildpacks:set https://github.com/heroku/heroku-buildpack-static.git
```

4. Create a `static.json` file which configures the Buildpack:
```
echo '{ "root": "dist/" }' >> static.json
```

5. Make sure everything is checked into Git:
```
git add .
git commit -m "First commit"
```

6. Push to Heroku:
```
git push heroku master
```

```
...
remote: -----> Compressing...
remote:        Done: 1.5M
remote: -----> Launching...
remote:        Released v1
remote:        https://ember-test-am.herokuapp.com/ deployed to Heroku
remote:
remote: Verifying deploy... done.
```

7. Your Gatsby site is running on Heroku. Let's check it out:
```
heroku open
```

#heroku/spa