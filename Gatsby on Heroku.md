# Gatsby on Heroku
Gatsby is a blazing fast modern site generator for React.
This quick start guide will have you running Gatsby on Heroku in no time.

This setup assumes knowledge of the Heroku CLI and that you've already installed & setup Gatsby itself.

## Jump into your terminal...
_Note: if you haven't done so already, initiate a Git repository in your working directory:_
```
git init
```

1. Create a new Heroku app for our Gatsby site to live on:
```
heroku create
```

2. Add the Node & Static Buildpacks:
```
heroku buildpacks:set heroku/nodejs --index 1
heroku buildpacks:add https://github.com/heroku/heroku-buildpack-static.git --index 2
```

3. Add the `heroku-postbuild` script to `package.json`:
```
{
  "scripts": {
    "heroku-postbuild": "gatsby build"
  }
}
```

5. Create a `static.json`  file and copy the following into it:
```
{
  "root": "public/",
  "headers": {
    "/**.js": {
      "Cache-Control": "public, max-age=0, must-revalidate"
    }
  }
}
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
remote:        https://gatsby-test-am.herokuapp.com/ deployed to Heroku
remote:
remote: Verifying deploy... done.
```

7. Your Gatsby site is running on Heroku. Let's check it out:
```
heroku open
```

#heroku/spa