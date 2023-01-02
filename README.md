# Awesome Cv Action

<img src="https://user-images.githubusercontent.com/4768226/210252649-ff3d1461-58e5-4670-9d50-be3f947e2216.png" width="100%" />

> A GitHub action to keep you Awesome CV up to date through continuous integration

## 🏆 How this action can help you ?

If you are an automation lover you will realize that one of the pain we need to automate is our resume...

By using a manual process we need to go through old versions, find the right one, update, reshape etc...

Nowaday a few open source project help to support that pain from an edition perspective such as : [Awesome-CV](https://github.com/posquit0/Awesome-CV) from [posquit0](https://github.com/posquit0) (based in Latex).

**This how i came up with the idea of automating the resume exactly like a software!**

A simple pipeline support 4 steps for you:

1. compile your resume into a .pdf
2. create a git tag and a github release
3. Upload the resume as a pdf to the github release.
4. And voila ! You will have an up to date resume accessible from anywhere through a simple url like : [YOUR RESUME REPO URL]/releases/download/latest/resume.pdf

## 🚀 Usage


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

## 🎄 Influence

A few years ago i already created this pipeline automation through Github app, Heroku and https://latexonline.cc. (https://github.com/olivierodo/gh-cv-assistant)
That was a complicated setup... It helped me a lot to keep my resume update to date and accessible (i just love to send the link of the pdf hosted on github when someone is asking for my resume 😇)
No i more that happy to propose a simple version using Github Action. It's all what i needed to simplify this workflow!

### ⭐️ References

* [Awesome-CV](https://github.com/posquit0/Awesome-CV) 
* [Old version using Github app](https://github.com/olivierodo/gh-cv-assistant) 
* [My Resume](https://github.com/olivierodo/Awesome-CV) (I'm open to job proposal!)


### Keywords

* automation
* Continuous integration
* Resume
* Job
* Awesome CV
* CV
* Latex
* RestQA

### Promo (RestQA)

RestQA is the Best in Class Microservice Test Automation Framework.
[Give a try](https://github.com/restqa/restqa) 🚀

