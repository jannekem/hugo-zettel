# Hugo Zettel

A Hugo theme for building your own Zettelkasten as a static website.

Based on the [Hugo Tailwind CSS starter theme](https://github.com/dirkolbrich/hugo-theme-tailwindcss-starter).

## Features

- add links between notes from front matter
- browse notes by tags
- add `entry: true` to add a not to the front page as an entry note
- set up to use [Tailwind CSS](https://tailwindcss.com) - v1.4
- use [Hugo Pipes](https://gohugo.io/hugo-pipes/) to build and load css based on `dev` or `build` environment
- purge unused css classes with [PurgeCSS](https://www.purgecss.com) for `build`, but __not__ in `dev`

## Prerequisites

Make sure to install `postcss-cli` and `autoprefixer` globally in your environment, as Hugo Pipe’s PostCSS requires it. This is mentioned in the [Hugo Docs](https://gohugo.io/hugo-pipes/postcss/).

```bash
npm install -g postcss-cli
npm install -g autoprefixer
```

Navigate to the theme directory and install the necessary Node packages:

```bash
npm install
```

## Theme development

- start a server to develop with `exampleSite`

```bash
hugo server -s exampleSite --themesDir=../.. --disableFastRender
```

## Deploy to Netlify

If you use this theme and want to deploy your site to [Netlify](https://www.netlify.com/), you *MAY* encounter a build error which contains the following line:

```bash
ERROR {your deploy time here} error: failed to transform resource: POSTCSS: failed to transform "css/styles.css" (text/css): PostCSS not found; install with "npm install postcss-cli". See https://gohugo.io/hugo-pipes/postcss/
```

That is, Netlify doesn't know the `npm` dependencies of this starter theme yet. For this to fix, please add a `package.json` file to the root of your repo with the content:

```json
{
    "name": "my-site",
    "version": "0.0.1",
    "description": "that is my-site",
    "repository": "https://github.com/you/my-site",
    "license": "MIT",
    "devDependencies": {
        "@fullhuman/postcss-purgecss": "^2.1.0",
        "autoprefixer": "^9.7.4",
        "postcss": "^7.0.27",
        "postcss-cli": "^7.1.0",
        "postcss-import": "^12.0.1",
        "tailwindcss": "^1.2.0"
    },
    "browserslist": [
        "last 1 version",
        "> 1%",
        "maintained node versions",
        "not dead"
    ]
}
```

This introduces the dependencies Tailwind CSS and PostCSS need, Netlify will run the installation automatically on deploy.

### Environment variables

To make the distinction between `development` and `production` environments work, add an environment variable `HUGO_ENV = "production"` to your site settings under `Settings` → `Build & deploy` → `Environment`.

Or use a `netlify.toml` for a [file-based configuration](https://docs.netlify.com/configure-builds/file-based-configuration/).

## Reference

Documentation for Hugo's [PostCSS setup](https://gohugo.io/hugo-pipes/postprocess/).

Documentation for [Tailwind CSS setup of calling PurgeCSS manually](https://tailwindcss.com/docs/controlling-file-size#setting-up-purgecss-manually).
