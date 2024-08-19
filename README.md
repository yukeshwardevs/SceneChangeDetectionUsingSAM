<img width="960" alt="ScdSAMoutput" src="https://github.com/user-attachments/assets/b8bba0f6-d173-49dd-8e29-bd83ab53e602">
Challenges faced: 
  1. Video has delay between speaker voice and actual scene change. So, as the transcripts are aligned to scene change, some transcript grouping may seem to take transcript from next scene.
  2. Not able to fetch video directly from youtube as YouTube blocks from downloading.

##Parameters used for detecting scene change:
  ###Mask threshold: 
    Lower Threshold (e.g., 0.05): The model becomes more sensitive to even small changes in the mask. This could lead to detecting more scene changes, even when the change is minor or due to small variations like lighting shifts or slight camera movements.
    Higher Threshold (e.g., 0.25): The model becomes less sensitive, meaning it will only detect significant changes in the mask. This might result in fewer scene changes being detected, focusing on more substantial alterations in the background.
  ###Tone threshold:
    Lower Threshold (e.g., 0.1): The model becomes very sensitive to small changes in color distribution. It might detect scene changes even with slight variations in lighting, color tones, or minor edits in the video.
    Higher Threshold (e.g., 0.5): The model becomes less sensitive to minor color differences. It will focus on more significant changes, such as a switch between completely different scenes, and might ignore smaller variations.

##Notebook 1:
  In this notebook SAM is used to analyse complete image frame ectracted from the video.
##Notebook 2:
  In this notebook SAM is used to analyse by extracting backckground and determine scene change based on color tone and mask change [Mask generated my predict method of SAM].
