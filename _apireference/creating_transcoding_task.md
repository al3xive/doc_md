---
title: Creating Transcoding Task
position: 3.1
type: GET
description: 
parameters:
  - name: access token
    content: your token
content_markdown: |-
  This route is for creating a transcoding task.

left_code_blocks:
  - code_block: |-
      curl https://api.qencode.com/v1/create_task -d token=76682314a86ed377730873394f8172f2 

    title: CURL
    language: json

  - code_block: |-
      
    title: Postman
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