---
name: northlit-video
description: Animate an image into a video clip with Northlit
---

Create a video clip with Northlit:

(the user's request)

1. Pick the source image: a direction's mock (`list_directions` / `view_mock`), an image generated this session, or any hosted https URL. No image yet? Generate one first (the northlit-image skill).
2. Optionally call `image_to_prompt` with scope "video" to turn the image into motion direction.
3. Call `generate_video` with the imageUrl and motion prompt.
4. Poll `check_video_status` with the URLs it returned, echoing the same model/duration/resolution — the finished clip is billed on the completed poll.
5. Call `save_video` to keep it: provider URLs expire, saving rehosts the mp4 durably onto the run.
