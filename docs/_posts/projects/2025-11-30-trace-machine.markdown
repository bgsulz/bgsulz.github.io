---
layout: post
title: "Trace Machine"
subtitle: "Image provenance toolkit and correlation engine"
thumbnail: "/assets/heros/Trace Machine.png"
tags: [project, design]
permalink: /tracemachine/
startdate: "2025-11-01 00:00:00"
---

[Trace Machine](https://tracemachine.com) is an image provenance toolkit. Upload or link an image, and the website will analyze it for traces of synthetic media.

[Visit site](https://tracemachine.com){: .btn}

- Key details of the image's **C2PA manifest** are shown. All of [OpenAI's models sign their images](https://help.openai.com/en/articles/8912793-c2pa-in-chatgpt-images) and so does [Google's Nano Banana Pro](https://blog.google/technology/ai/ai-image-verification-gemini-app/) in certain apps.
    - *Mind you, I haven't managed to find a single example of a Nano Banana Pro generation with any detectable C2PA manifest.*
    - C2PA data may also be useful for verifying that an image is straight from a camera, or edited with non-AI programs. [Certain devices and services](https://c2paviewer.com/supported-devices) embed it at the time of creation or editing.
    - C2PA data is easy to scrub -- just take a screenshot, for example -- so Trace Machine also reports on C2PA data for previously analyzed images that are very visually similar. If an AI-generated image (with C2PA data) was analyzed, its manifest will likely show up if you analyze a screenshot of that image.
- Key details of the image's **EXIF metadata** are shown. Common local AI image frontends like [Automatic1111](https://github.com/AUTOMATIC1111/stable-diffusion-webui) (formerly ubiquitous, now dated) and [ComfyUI](https://github.com/comfyanonymous/ComfyUI) embed details of their prompt and workflow into the image.
    - *EXIF metadata can be freely edited. The presence of these prompt/workflow details are mild evidence of AI generation, but their absence is no evidence in any direction.*
    - As EXIF metadata can be freely edited, no data is shown for visually similar images (it would be too easy to "poison the well" with false metadata.)
- Each image has a poll to monitor human consensus. You can mark an image as human-generated, AI-edited, or AI-generated if you are reasonably confident of its origin.
    - Similar to C2PA metadata, Trace Machine sums votes from all previously analyzed images that are very visually similar (so an image and a screenshot of that image don't have two disconnected polls.)
    - *Human consensus should be almost entirely disregarded for very high-importance images -- anything for which bad actors have a strong incentive to stuff the ballot box. Research these images independently.*

More features (and a browser extension enabling easy in-place analysis) to come.