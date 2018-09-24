---
title: Stitching videos with /v1/start_encode
position: 1.1
type: GET
description: 
parameters:
  - name: access token
    content: your token
content_markdown: |-
  This route is for stitching videos using /v1/start_encode
  
  Key thing is using “stitch” param for /v1/start_encode method instead of “uri” and instead of “source” query attribute for /v1/start_encode2 method.
  Same format of JSON array is used for both methods. You can specify just urls to input videos as stitch array elements:
  {: .info }

left_code_blocks:
  - code_block: |-
      {
        "output" : "thumbnails",
        "destination": {
          "url":"s3://nyc3.digitaloceanspaces.com/qencode3/test/thumb/bbb/",
          "key":"abcde12345",
          "secret":"abcde12345",
          "permissions": "public-read"
        },
        "interval": 30,
        "width" : 320,
        "height" : 240
      }

    title: Example with URLs
    language: json

  - code_block: |-
      [
        {"url" : "https://yourserver.com/video1.mp4"},
        {
          "url" : "https://yourserver.com/video2.mp4", 
          "start_time": "120.0", 
          "duration": "60.57"
        }
      ]

    title: Example with Object Format
    language: json
  
  - code_block: |-
      curl https://api.qencode.com/v1/start_encode2 \
        -d task_token=b49e034d198262f1d5d15ed9f3cb8ee1 \
        -d stitch='[
            {"url" : "https://yourserver.com/video1.mp4"},
            {
             "url" : "https://yourserver.com/video2.mp4", 
            "start_time": "120.0", 
            "duration": "60.57"
            }
          ]
        -d profiles=5a2a846a26e88

    title: CURL
    language: json

right_code_blocks:
  - code_block: |-
      {"error":0,"upload_url":"https:\/\/storage.qencode.com\/v1\/upload_file","task_token":"471272a512d76c22665db9dcee893409"}

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