# Project Frame Interpolation and Upscaling for Video

For computational complexity reasons, I have inverted the operations, first I interpolate the frame rate and then I upscale.

### Requires:
#### Used Libraries:
- OpenCV
- NumPy
- matplotlib
- msvcrt
- os
- tkinter
- time
- json
- ttkbootstrap
- ttkthemes
- webbrowser

### Instructions:

- Run GUI.py
- Select the video
- Select parameters
- Run

### Processing Steps:

#### Frame Interpolation:
1. `demo.py` passes the video's path to the frame interpolation function.
2. The video interpolation function increases the number of frames by first calculating the optical flow between frame pairs both forward and backward, then interpolating n new frames between each frame pair.
3. The original frames are discarded.
4. The video is saved.

#### Video Upscaling:
5. `demo.py` calls the video upscaling function, passing it the path of the interpolated video. For each frame, the function invokes the bilinear upscaling function.
6. Once a frame has been upscaled, filters are applied, and the frame is saved to the new video, until completion.

### End of System

### Legend:

- `zoom_factor`:                        Desired upscaling factor
- `iterazioniUpscaling`:                Number of times upscaling is performed on the same frame
- `numInterpolateFrames`:               Number of frames to interpolate for each frame pair

- final_upscaling = initial_resolution * (zoom_factor ** iterations)

- `SelectVideo` accepted strings:       Tunnel, Waves, Rallye, Smoke, Monochrome, Lights, Bees, Lights10
- `SelectFilters` accepted strings:     Bees, Bees360p, Lights10, None

- Final FPS after interpolation:  FPS = numInterpolateFrames * (numFramesIniziale - 1)

- Codec used: XVID

- `filterValues` Legend:

    * `blur_k_dim`:                       Initial blurring kernel size
    * `blur_sigma_x`:                     Initial blurring sigma
    * `sharp_k_center`:                   Center value of the sharpening kernel
    * `Laplacian_k_size`:                 Laplacian kernel size (lower values detect finer edges)
    * `threshold_value`:                  Threshold value (precision of edges included in binarization, 0-255, lower values include more edges)
    * `blur_k_dim_2`:                     Final blurring kernel size
    * `blur_sigma_x_2`:                   Final blurring sigma
    * `showEdges`:                        Keep as false, allows enabling or disabling the visualization of edge detection overlaid on the image


Coded by Roberto Tallarini

