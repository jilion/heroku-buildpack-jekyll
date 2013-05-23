# Heroku Jekyll Buildpack

The Jekyll Buildpack will look for a file named `_config.yml` in the app root
and use Jekyll to generate the site.

The buildpack uses the `Gemfile.lock` in your project to detect the `jekyll` and
`RedCloth` versions to use.

## Usage

This buildpack should be used in coordination with the Ruby buildpack using
[`heroku-buildpack-multi`](https://github.com/ddollar/heroku-buildpack-multi).
To serve your site, we recommend using
[`rack-jekyll`](http://rubygems.org/gems/rack-jekyll).

Add this language pack to your `BUILDPACK_URL`:
```bash
$ heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git
```

or, set it at creation time:
```bash
$ heroku create --stack cedar --buildpack https://github.com/ddollar/heroku-buildpack-multi.git
```

Don't forget to create a `.buildpacks` file at the root of your project:

```bash
https://github.com/jilion/heroku-buildpack-jekyll#production
https://github.com/heroku/heroku-buildpack-ruby
```
