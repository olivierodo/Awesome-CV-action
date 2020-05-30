# Awesome Cv Action

> A GitHub action to keep you Awesome CV up to date through continuous integration

## How this action can help you ?

If you are an automation lover you will realize that one of the thing we all need to automate is our resume...
This is a major pain for everyone to go through the old version then update reshape etc...
Nowaday a few open source project help to support that pain from an edition point of view like : [Awesome-CV](https://github.com/posquit0/Awesome-CV) from [posquit0](https://github.com/posquit0).
This how i came up with the idea what if we can have a pipeline for our resume ? 
A simple pipeline will do 4 simple steps for you:

1. compile your resume into a .pdf
2. create a tag and a git release
3. Upload the resume as a pdf to the release.
4. And voila ! You will have an up to date resume accessible from anywhere through a simple url like : [YOUR RESUME REPO URL]/releases/download/latest/resume.pdf

## Usage


First you will need to have add the action to a repository forked from [Awesome-CV](https://github.com/posquit0/Awesome-CV) 

If your resume filename is `john-doe.tex`, run it like this:

### Creates 2 tags (latest and v[VYYDDMM.HH.MM])

This allowing to have an extra tag named `latest` allowing the use the same url to access your resume from anywhere (portfolio, linkedin, email, etc)

```yaml
name: Awesome-CI

on: [push]

jobs:
  awesome-cv-job:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v1
    - uses: olivierodo/awesome-cv-action@0.0.1
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      with:
        FILE_NAME: 'john-doe.tex'
        LATEST_TAG: 'false' # set to false if you don't want an auto tag of latest (default: true)

```

### Creates 1 tags (v[YYDDMM.HH.MM])

```yaml
name: Awesome-CV-CI

on: [push]

jobs:
  awesome-cv-job:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v1
    - uses: olivierodo/awesome-cv-action@0.0.1
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      with:
        FILE_NAME: 'john-doe.tex'
        LATEST_TAG: 'false' # set to false if you don't want an auto tag of latest (default: true)

```

A simple example accessible on my repository: https://github.com/olivierodo/Awesome-CV


### References

* [Awesome-CV](https://github.com/posquit0/Awesome-CV) 
* [Old version using Github app](https://github.com/olivierodo/gh-cv-assistant) 


### Keywords

* automation
* Continuous integration
* Resume
* Job
* Awesome CV
* CV
* Latex
* RestQa
  

### PROMO : Do you know RestQa ? 

Restqa is an open automation framework based on Gherkin.
A few step and your Test automation framework is setup. No dependency the framework is ready to be plug to any of your project components
[Give a try](https://github.com/restqa) 🚀
