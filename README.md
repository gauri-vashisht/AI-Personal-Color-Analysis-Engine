# Personal-Stylist
AI Personal color analyst that tells you what looks great on you and what doesn't, on the basis of an image that is uploaded. this uses CV2, gradio, ScikitLearn K means, mediapipe

https://1d74f954a0e1465391.gradio.live/


<img width="1274" height="485" alt="image" src="https://github.com/user-attachments/assets/e2949aa5-7bc7-41fe-8e11-0c5e3956f992" />

The engine operates like a assembly line with four major stages: Face Parsing, Feature Extraction, Mathematical Classification, and Presentation.

the code uses MediaPipe Face Mesh to locate specific anatomical coordinates on the face.
The array safe_zone_indices targets 16 specific landmarks on the forehead and cheeks. The code then samples a small 5x5 pixel grid around each landmark. This guarantees that the color analysis is based purely on clean skin.
Even on clean skin, overhead lighting creates glare and shadows. If you average all the pixels together, the result will be muddy and inaccurate.To solve this, the code uses Unsupervised Machine Learning ($K$-Means) to group all the sampled skin pixels into 3 distinct color clusters. It then isolates the largest cluster, successfully separating your true skin tone from random lighting anomalies
