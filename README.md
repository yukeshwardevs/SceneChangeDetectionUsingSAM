<img width="960" alt="ScdSAMoutput" src="https://github.com/user-attachments/assets/b8bba0f6-d173-49dd-8e29-bd83ab53e602">

# Scene Change Detection in Videos using Segment Anything Model (SAM)

This project focuses on detecting scene changes in videos by analyzing video frames using the Segment Anything Model (SAM). The aim is to efficiently segment video transcripts based on scene changes, making it easier to understand the video's structure.

## Challenges Faced

1. **Voice-Scene Delay:**
   - **Issue:** There's often a delay between the speaker's voice and the actual scene change in the video. As a result, aligning the transcripts with scene changes can sometimes cause transcripts from the next scene to be grouped incorrectly.
   - **Impact:** This misalignment may affect the accuracy of the transcript grouping, leading to less coherent or contextually mismatched transcript segments.

2. **YouTube Video Fetching:**
   - **Issue:** Directly fetching videos from YouTube is challenging due to restrictions that block downloading.
   - **Impact:** This limitation requires alternative methods for processing YouTube videos, such as using downloaded videos or stream-based processing.

## Parameters for Detecting Scene Changes

### 1. Mask Threshold
   - **Lower Threshold (e.g., 0.05):**
     - The model becomes more sensitive to minor changes in the mask.
     - Detects more scene changes, even from small variations like lighting shifts or camera movements.
   - **Higher Threshold (e.g., 0.25):**
     - The model is less sensitive, focusing only on significant mask changes.
     - Results in fewer detected scene changes, targeting substantial alterations in the background.

### 2. Tone Threshold
   - **Lower Threshold (e.g., 0.1):**
     - The model is highly sensitive to minor color distribution changes.
     - Detects scene changes even with slight lighting or color tone variations.
   - **Higher Threshold (e.g., 0.5):**
     - The model is less sensitive to minor color differences.
     - Focuses on significant changes, like a complete scene switch, while ignoring smaller variations.

## Notebooks

### Notebook 1: Complete Image Frame Analysis using SAM
   - **Overview:** This notebook utilizes SAM to analyze the entire image frame extracted from the video.
   - **Objective:** Detect scene changes based on overall frame analysis without focusing on specific regions.

### Notebook 2: Background Extraction and Analysis using SAM
   - **Overview:** This notebook leverages SAM to extract the background and determine scene changes based on color tone and mask changes.
   - **Details:**
     - **Mask Analysis:** Mask generated by SAM's `predict` method is used to detect changes.
     - **Color Tone Analysis:** Scene changes are determined by variations in the background’s color tone.

## Conclusion

This project showcases an approach to detecting scene changes in videos by combining frame analysis and background extraction using SAM. Despite challenges like voice-scene delays and YouTube restrictions, the method aims to improve transcript segmentation and video analysis.
