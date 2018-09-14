---
title: Adding logo/watermark
position: 1.1
type: GET
description: 
parameters:
  - name: access token
    content: your token
content_markdown: |-
  This route is for adding logo or watermark to output video.
  
  An object describing logo / watermark should be inserted into “format” element:
  {: .info}

left_code_blocks:
  - code_block: |-
      "format": [
       {
        "output": "mp4",
         ...
          "logo": {
            "source": "https://yourserver.com/watermark.png",
            "x": 10,
            "y": 10
          }
        }
      ]

    title: Example
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