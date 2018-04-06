# INSTALL
```
$ meteor add fourseven:scss
$ meteor add poetic:materialize-scss
$ meteor remove materialize:materialize # if you have materialize installed
```

# SCSS
Add the following lines to your last-loaded scss file (E.G. main.scss):
```
// If you want to override materialize sass variables you can uncomment the following:
// @import "{poetic:materialize-scss}/sass/components/_color.scss";
// $primary-color: color("blue", "lighten-2");

// import main scss file
@import "{poetic:materialize-scss}/sass/materialize.scss";
```

# ICONS
Icons are automatically imported from this package.

You do NOT have to add an additional head element mentioned at http://materializecss.com/icons.html.

Read more about the MaterialIcons at https://google.github.io/material-design-icons/

# JAVASCRIPT
Javascript is automatically imported from this package.

# CHANGE LOG

- 2018-04-06 update to materializecss [0.100.2](https://github.com/Dogfalo/materialize/tree/v0.100.2#changelog)
- 2016-04-18 update to materializecss [0.97.6](https://github.com/Dogfalo/materialize/tree/v0.97.6#changelog)
- 2016-01-28 update to materializecss [0.97.5](https://github.com/Dogfalo/materialize/tree/v0.97.5#changelog)
- 2015-11-22 update to materializecss [0.97.3](https://github.com/Dogfalo/materialize/tree/v0.97.3#changelog)
  - We rewrote the package as a fork and archived the previous gitrop. If you are looking for code in a version lower than 1.97.3, please check the archived [repo](https://github.com/poetic/meteor-materialize-sass-archived). (*Breaking*)

- 2015-10-01 update package for METEOR@1.2 (*Breaking*)
  - fourseven:scss is updated to 3.3.3_1
  - scss.json is not used anymore.
  - index.scss is not autoupdated anymore, you need to manullay update index.scss.

- 2015-06-26 upgrade to [0.97.0](https://github.com/Dogfalo/materialize/tree/v0.97.0#changelog)
  - Icon Change (*Breaking*):

    `<i class="mdi-content-add"></i>` is still supported.

    However you should use `<i class="material-icons">add</i>` instead as
    metioned in the materialize [doc](http://materializecss.com/icons.html).

# FOR MAINTAINERS

## Updating to New Versions of MaterializeCSS

Fetch latest changes from `Dogfalo/materialize`:

```sh
$ git checkout master
$ git pull https://github.com/Dogfalo/materialize.git master --tags
```

Create feature branch off of `meteor` for version upgrade:

```sh
$ git checkout meteor
$ git checkout -b materialize-v0.100.2
```


Merge in changes but do not commit:

```sh
$ git merge --no-commit --no-ff master
```

Make sure:

1. Only relevant SCSS/font/package changes are included.
2. New files have been added to `package.js`.
3. `README.md` hasn't been mangled.

Test and commit changes:

```sh
$ npm run test
$ git commit -m "Pull in Dogfalo/materialize v0.100.2"
# Update Meteor package version
$ git commit -m "Bumped Meteor package version to v1.100.2"
$ git push
```

And then open a PR! A maintainer will `meteor publish` once the PR is approved.

Pat yourself on the back for being awesome.
