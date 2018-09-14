---
title: Getting Access Token
position: 1.1
type: GET
description: 
parameters:
  - name: access token
    content: your token
content_markdown: |-
  This route is for getting the access token.

left_code_blocks:
  - code_block: |-
      curl https://api.qencode.com/v1/access_token -d api_key=5a2a846a26ace 

    title: CURL
    language: json

  - code_block: |-
      
    title: Postman
    language: json
right_code_blocks:
  - code_block: |-
      {"error":0,"token":"1e1111fec48cc52060ca27312ed983ce","expire":"2018-09-03T14:01:56"}

    title: Response
    language: json
  - code_block: |-
      {
        "success": false,
        "result": null
      }
    title: Error
    language: json
---