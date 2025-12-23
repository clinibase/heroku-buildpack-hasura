# Hasura Buildpack

This is a [Heroku buildpack][0] for bundling a compatible [hasura][1]
binary with your environment.

## Versions

* Buildpack:   `0.2`
* hasura: `2.48.6` by default

## Usage

[Add this buildpack][2] to your Heroku application to install the `hasura-cli` and `graphql-engine` binaries into the dynos:

```bash
$ heroku buildpacks:add https://github.com/clinibase/heroku-buildpack-hasura.git
```

If you want to use a `hasura` version other than 2.48.6, set
`HASURA_VERSION`:

```bash
heroku config:set HASURA_VERSION="2.48.0"
```

### Clearing Repo Cache

Remember to clean your repository cache if you are updating the version of
buildpack. To do that, run:

```bash
$ heroku plugins:install https://github.com/heroku/heroku-repo.git
$ heroku repo:purge_cache -a appname
```

## Troubleshooting

If you run into issues when trying to deploy with this buildpack, make sure your
app is running on `cedar-14` or `heroku-16`. You can check this with:

```bash
$ heroku stack
```

[0]: http://devcenter.heroku.com/articles/buildpacks
[1]: https://hasura.io/
[2]: https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app