---
title: Generating Thumbnails
position: 1.1
type: GET
description: 
parameters:
  - name: access token
    content: your token
content_markdown: |-
  This route is for generating thumbnails. 

  There are two ways of thumbnails creation with Qencode API:
  {: .info }
    - You can generate individual thumbnails at specified moments of a video (specified in % of video length).
    
    - You can create thumbnails for the whole video basing on an interval value between each thumbnail specified in seconds. When using this way a WebVTT file can be also seamlessly generated. WebVTT (https://www.w3.org/TR/webvtt1/) is a standard many players support to display thumbnails in a tooltip when a viewer hovers the control bar.

  Individual thumbnails

left_code_blocks:
  - code_block: |-
      {
        "output": "thumbnail",
        "time": "0.15",
        "width": "920",
        "height": "500",
        "destination": "",
        "user_tag": "15_920x500"
      }

    title: Example
    language: json
  
  - code_block: |-
      curl https://api.qencode.com/v1/start_encode2 \
        -d task_token=b49e034d198262f1d5d15ed9f3cb8ee1 \
        -d query='{"query": {
        "source": "https://qa.qencode.com/static/test_mini.mp4",
        "format": [
             {
                    "output": "mp4",
                    "destination": {
                      "url":"s3://nyc3.digitaloceanspaces.com/qencode3/test/test_mini.mp4",
                      "key":"abcde12345",
                      "secret":"abcde12345",
                      "permissions": "public-read"
                    },
                     "framerate": "29.97",
                     "keyframe": "25",
                     "file_extension": "mp4",
                     "size": "360x240",
                     "start_time": "10",
                     "duration": "20"
                   },
                   {
                     "output": "thumbnail",
                     "time": "0.15",
                     "width": "320",
                     "height": "240",
                     "destination": {
                       "url":"s3://nyc3.digitaloceanspaces.com/qencode3/test/thumb/15_320x240.png",
                       "key":"abcde12345",
                       "secret":"abcde12345",
                       "permissions": "public-read"
                      },
                     "user_tag": "15_320x240"
                    },
                   {
                     "output": "thumbnail",
                     "time": "0.50",
                     "width": "320",
                     "height": "240",
                     "destination": {
                       "url":"s3://nyc3.digitaloceanspaces.com/qencode3/test/thumb/50_320x240.png",
                       "key":"abcde12345",
                       "secret":"abcde12345",
                       "permissions": "public-read"
                      },
                     "user_tag": "50_320x240"
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