    #Implementation Creation
    Lane Detection: Canny Edge Detection and Hough Transform
    
    #import libraries
import numpy as np
import matplotlib.pyplot as plt
    
    #Convert to grayscale
  def process_image(image):

  
  gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
    
    # Apply Gaussian blur
  blur = cv2.GaussianBlur(gray, (5, 5), 0)
    
    # Canny Edge Detection
  edges = cv2.Canny(blur, 50, 150)
    
    # Define Region of Interest (ROI)
  height, width = edges.shape
  roi = np.array([[(0, height), (width, height), (width//2, height//2)]], dtype=np.int32)
    
    # Create a mask with the ROI
  mask = np.zeros_like(edges)
  cv2.fillPoly(mask, roi, 255)
  masked_edges = cv2.bitwise_and(edges, mask)
    
    # Hough Transform to detect lines
  lines = cv2.HoughLinesP(masked_edges, 1, np.pi/180, 50, minLineLength=50, maxLineGap=150)
    
    # Draw lines on the original image
  line_image = np.zeros_like(image)
  if lines is not None:
        for line in lines:
            x1, y1, x2, y2 = line[0]
            cv2.line(line_image, (x1, y1), (x2, y2), (0, 255, 0), 5)
    
    # Combine the original image with the line image
  combined_image = cv2.addWeighted(image, 0.8, line_image, 1, 0)
    
  return combined_image

    # Load a sample image
image = cv2.imread('road.jpg')  # Replace 'road.jpg' with your road image file
output_image = process_image(image)

    # Display the result
plt.figure(figsize=(10, 6))
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Detected Lane Lines')
plt.axis('off')
plt.show()
