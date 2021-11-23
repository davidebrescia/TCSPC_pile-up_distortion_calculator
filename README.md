# TCSPC Pile-Up Deformation Plotter

## Time-Correlated Single Photon Counting (TCSPC) pile-up
What is it? I try to simplify at my best:

- A laser emits a pulse of light with a certain shape (e.g., gaussian, triangular, ...).
- The pulse is composed of a certain number of photons (photons).
- Each of these photons has a probability 'r' of reaching the detector, being absorbed and detected.
- The detector outputs the arrival time-stamp of the ***very first*** photon detected.  

What's the distribution of these arrival times?  
This script answers.

## Some examples
Let's analyze some laser pulse shapes.

From the left to the right, the "average number of photons impinging on the detector per pulse" decreases: 10, 1, 0.1.  
This parameter is somehow a measure of the pile-up. 

Important remark:  
When the parameter is 0.1 (figures on the right), the histogram of the very-first-photon arrival-times (blue) is practically equal to the original laser pulse shape. In fact, the 0.1 situation corresponds to the famous "10% rule of thumb" that we find in literature. 

### Gaussian pulse
This is the typical laser pulse shape. 
Note that, although the pile-up effect is bad for N reasons, it is benefical from the point of view of the distribution variance (the width is smaller).  

![gauss](https://user-images.githubusercontent.com/92381157/143009953-64d7d197-cf91-47a6-b327-c332c4df79b7.png)

### Triangular pulse

![triangular](https://user-images.githubusercontent.com/92381157/143013951-f73e0f7e-1cad-49fb-b7cb-79f57edde317.png)

### Sawtooth pulse

![sawtooth](https://user-images.githubusercontent.com/92381157/143013998-7f8fbc2d-b2dd-42ec-b52f-4e4be42b5a53.png)

### Reversed sawtooth pulse
Just for fun. I don't think that this shape does exist. 

![saw_rev](https://user-images.githubusercontent.com/92381157/143014135-77ba3b48-98a6-4f4b-aad1-d1bef7ba3734.png)

### Rectangular pulse

![rect](https://user-images.githubusercontent.com/92381157/143014042-872b942b-8982-4484-a6ba-f1c06b46ac34.png)

### Semi-elliptical pulse
Again, just for fun.

![semi-ellipse](https://user-images.githubusercontent.com/92381157/143014370-8e157a5d-0655-436b-9743-560e56b42c1b.png)

### 'Dumbest Plot' Award
I don't know why, but it seems very dumb to me. Like a Barbapapa:  
<img src="https://user-images.githubusercontent.com/92381157/143014632-c3879ac4-0a07-4f22-a54b-a35426a6a65a.png" width="400" height="250">

## How it works
The problem is discretized into many time bins. From there, it's just a matter of probability computations.  
Anyways, the Python Notebook is fully commented and explained.
