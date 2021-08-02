# Count_fingers
Uses OpenCV to Count the number of fingers held up by a hand in a certain region of the frame.
Works best with high contrast between hand and background. You will propably need to adjust the thresholding limit to account for the brightness in your particular enviroment.

Works by selecting a region of interest in the frame, and initially finding the average values for the background with no hand. When a hand is introduced, the frame is grayscaled, thresholded, and the hand is segmented with contour detection. The hand contours is used to calculate the center of the hand, then a mask is made out of the thick outline of a circle centered at the hand center, radius relative to the size of the hand. Then fingers are counted by counting the numbers of contours within the circle outline. Contours from the wrist are ignored by assuming the hand comes up from below, such that contours too close to the bottom of the circle are ignored.
