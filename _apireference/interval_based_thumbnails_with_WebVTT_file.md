---
title: Interval-based Thumbnails
position: 1.1
type: GET
description: 
parameters:
  - name: access token
    content: your token
content_markdown: |-
  Example below specifies creation of 320x240 size thumbnails at each 30 seconds of a video.
  Thumbnails and WebVTT file will be saved into the folder specified in “url” attribute of “destination” object.


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

    title: Example
    language: json
  
  - code_block: |-
      curl https://api.qencode.com/v1/start_encode2 \
        -d task_token=b49e034d198262f1d5d15ed9f3cb8ee1 \
        -d query='{"query": {
            "source": "https://nyc3.digitaloceanspaces.com/qencode/bbb_sunflower_1080p_60fps_normal_339mb.mp4",
            "format": [
              {
                "output": "mp4",
                "destination": {
                  "url":"s3://nyc3.digitaloceanspaces.com/qencode3/test/bbb.mp4",
                  "key":"abcde12345",
                  "secret":"abcde12345",
                  "permissions": "public-read"
                },
                "file_extension": "mp4",
                "size": "320x240",
                "duration": 60
              },
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
            ]
          }
        } 

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