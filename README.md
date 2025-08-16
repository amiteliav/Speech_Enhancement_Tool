# Speech Enhancement / Removal Tool
Analytic speech enhancement or removal algorithm


# 1. Goal
This project implements an analytic speech enhancement and removal algorithm.
It can:
1. Enhance speech in noisy audio recordings.
2. Remove speech and isolate background noise.

The tool is based on traditional digital signal processing (DSP) techniques and is suitable for scenarios where explainability and fine control over the algorithm are important.


# 2. Overview of the Solution
The algorithm operates in the time–frequency domain using the following main steps:
1. Noise Estimation – Estimates the noise spectrum profile.
2. Speech Presence Probability (SPP) Estimation – Calculates the probability that speech is present in each time–frequency bin.
3. Pitch Tracking (f₀ detection) – Uses cepstrum analysis to detect the fundamental frequency of speech.
4. Harmonies-based Masking – Detects harmonic structures of speech and creates a mask.
5. Hysteresis Thresholding – Refines the mask by keeping only connected speech regions.
6. Voice Activity Detection (VAD) – Removes processing from non-speech frames.
7. Gain Mask Application – Applies the mask to either keep speech or keep noise.
8. Inverse STFT – Reconstructs the time-domain signal.

This design allows both:
1. Speech enhancement (keep speech, suppress noise).
2. Speech removal (keep noise, suppress speech).
