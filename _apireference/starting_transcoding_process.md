---
title: Starting Transcoding Process
position: 1.1
type: GET
description: 
parameters:
  - name: access token
    content: your token
content_markdown: |-
  This route is for starting the transcoding process.

left_code_blocks:
  - code_block: |-
      curl https://api.qencode.com/v1/start_encode \
        -d task_token=63adfb01d408081b10440682f3a64114 \
        -d uri="https://qa.qencode.com/static/test_mini.mp4" \
        -d start_time=10 \
        -d duration=20 \
        -d profiles=5a2a846a26e88,5a2a846a28604 \
        -d transfer_method=5aa2875489681 \
        -d payload="12345" \
        -d output_path_variables='{"category":"test_videos","video_name":"12345"}'

    title: CURL
    language: json

  - code_block: |-
      
    title: Postman
    language: json
right_code_blocks:
  - code_block: |-
      {"error":0,"status_url":"https:\/\/api.qencode.com\/v1\/status"}

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