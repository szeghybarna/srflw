# srflw



# Process of the edition of the webpage

## Initialize

Register on github

Create new public repo

clone your repo

git clone git@github.com:szeghybarna/srflw.git


Download and extract contents to your epo's root

https://codeload.github.com/szeghybarna/srflw/zip/refs/heads/main

git add + git commit

register on aws amplify

connect with github

build settings:

```yaml
version: 1
frontend:
  phases:
    preBuild:
      commands:
        - wget https://go.dev/dl/go1.21.5.linux-amd64.tar.gz -q
        - rm -rf /usr/local/go 
        - tar -C /usr/local -xzf go1.21.5.linux-amd64.tar.gz
        - rm -rf go1.21.5.linux-amd64.tar.gz
        - export PATH=$PATH:/usr/local/go/bin
        - go version
        - wget https://github.com/gohugoio/hugo/releases/download/v0.121.1/hugo_extended_0.121.1_Linux-64bit.tar.gz -q
        - tar -xf hugo_extended_0.121.1_Linux-64bit.tar.gz hugo
        - mv hugo /usr/bin/hugo
        - rm -rf hugo_extended_0.121.1_Linux-64bit.tar.gz
        - hugo version
    build:
      commands:
        - export PATH=$PATH:/usr/local/go/bin
        - go version
        - hugo
  artifacts:
    baseDirectory: public
    files:
      - '**/*'
  cache:
    paths: []

```