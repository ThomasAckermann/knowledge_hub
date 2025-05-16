#Robotics #ComputerVision 

Non-[[Linear]] [[Filter]] for noise suppression
The [[Filter]] response is based on the order (ranking) of the pixels contained in the [[Image]] area enclosed by the [[Filter]].

Steps:
- Select the kernel size
- sort all gray values in the area of the kernel
- Determine the average gray value from the sorted pixels
- Select the pixel as the new value