# Simple Rules For Losing Weight

[Hugo Framework](https://gohugo.io/) based repository of [https://simple-rules-for-losing-weight.com/](https://simple-rules-for-losing-weight.com/). Hosted on [AWS Amplify](https://aws.amazon.com/amplify/). Daily deployments are made using [Lambda](https://aws.amazon.com/pm/lambda/) and [Amazon EventBridge](https://aws.amazon.com/eventbridge/).

Build settings on AWS Amplify:

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

Python AWS Lambda function:

```python
import json
import urllib.request

def lambda_handler(event, context):
    r = urllib.request.Request(
        'https://webhooks.amplify.eu-central-1.amazonaws.com/prod/webhooks?id=8a74af49-923d-4fa5-8159-f9cfba32c60c&token=6LeBZwuFTi0HbFhcs3yhfXLKJqtDw6UrbdgrIXzFes',
        data=json.dumps({}).encode('utf8'),
        headers={
            'Content-Type': 'application/json'
        },
        method='POST'
    )
    urllib.request.urlopen(r)
    return
```