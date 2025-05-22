## Complete List of Unique Questions from Provided Exam Papers

Below is a comprehensive, de-duplicated list of all unique questions extracted from the provided CS408 Computer Vision exam papers. Where questions involve data tables or mathematical expressions, these are included in the correct format. For clarity, similar questions from different years are merged, and subparts are listed for completeness.

---

### 1. Clustering and Classification

| No.   | Question                                                                                                                                                                                                                                                                                |
| :---- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | What is the main difference between clustering and classification?                                                                                                                                                                                                                  |
| 2 | Discuss the main challenges associated with selecting a clustering algorithm and elaborate on the use of distance as a pair-wise similarity measure.                                                                                                                                |
| 3 | How can the clustering quality of any partition of the data be measured?                                                                                                                                                                                                            |
| 4 | Briefly describe how k-means algorithm works and list its strengths and weaknesses.                                                                                                                                                                                                 |
| 6 | When applying the k-means clustering algorithm for a given set of data points, if different starting positions were used for the centers in separate instances, will the algorithm always converge to the same solution? Explain your answer.                                       |
| 7 | If clusters are to be meaningful, they should be invariant to transformations natural to the problem. <br> a) Suggest a method to obtain invariance to displacement and scale changes. Will this work for all the cases? <br> b) What can be done to obtain invariance to rotation? |
| 9 | Compare and contrast hierarchical clustering and k-means clustering.                                                                                                                                                                                                                |

#### K-means Clustering Data Problems

**Given Data Table (common across years):**

| ID | Dimension 1 | Dimension 2 |
| :-- | :-- | :-- |
| A | 1 | 1 |
| B | 8 | 6 |
| C | 20 | 3 |
| D | 21 | 2 |
| E | 11 | 7 |
| F | 7 | 7 |
| G | 1 | 2 |
| H | 6 | 8 |

- Find 3 clusters using k-means clustering algorithm. Assume initial cluster centroids are defined by A, B, and C. Provide a graphical representation of the clusters found.

**Another Data Table:**


| ID | Age |
| :-- | :-- |
| A | 1 |
| B | 2 |
| C | 3 |
| D | 11 |
| E | 12 |
| F | 13 |
| G | 21 |
| H | 22 |
| I | 23 |

- Assume you use k-means clustering to group the people by age into 3 groups. How many steps would be needed for the algorithm to converge if you start with centroids defined by A, B, and C?

**Another Data Table:**

Given eight points: A1(2,10), A2(2,5), A3(8,4), A4(5,8), A5(7,5), A6(6,4), A7(1,2), A8(4,9).

- Use k-means algorithm to find the three cluster centers after the first iteration considering initial cluster centers A1(2,10), A4(5,8), A7(1,2), using city block distance.

---

### 2. Support Vector Machines (SVM)

| No. | Question                                                                                                                                                                                                                                                                                                                    |
| :-- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 11  | Briefly explain how SVM works. Is it a supervised classifier?                                                                                                                                                                                                                                                               |
| 12  | Consider the following training data from the categories: <br> $\omega_1: (1,1)^T, (2,2)^T, (2,0)^T$ <br> $\omega_2: (0,0)^T, (1,0)^T, (0,1)^T$ <br> a) Plot the six training points and construct by inspection the weight vector for the optimal hyperplane and the optimal margin. <br> b) What are the support vectors? |
| 13  | Using XOR problem as an example, discuss the SVM classification for linearly non-separable data.                                                                                                                                                                                                                            |
| 14  | What happens when there is no clear hyperplane in SVM? Explain the concept of mapping data into a higher dimension (kernelling).                                                                                                                                                                                            |
| 15  | Can a similar approach (kernelling) be used for the XOR Problem? Explain.                                                                                                                                                                                                                                                   |
| 16  | When your data is imbalanced, is SVM a good approach? Explain.                                                                                                                                                                                                                                                              |


---

### 3. Feature Detection and Description

| No. | Question                                                                                                                                                                                                                                                                                                                                                                                                                    |
| :-- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 17  | List the main steps of Harris Corner Detector.                                                                                                                                                                                                                                                                                                                                                                              |
| 18  | Are Harris corners invariant to rotation? Why or why not?                                                                                                                                                                                                                                                                                                                                                                   |
| 19  | What defines whether a feature is good or bad? Are corners considered as better features than edges? Why?                                                                                                                                                                                                                                                                                                                   |
| 20  | Consider the matrix<br><br>$$M = \begin{bmatrix} I_x^2 & I_x I_y \\ I_x I_y & I_y^2 \\ \end{bmatrix}$$<br><br>The Harris corner detection algorithm computes a 2 x 2 matrix at each pixel based on the first derivatives at that point and then computes the two eigenvalues of the matrix. Explain how you can use the two eigenvalues to label each pixel as a locally smoothed region, an edge point, or a corner point. |
 |
|1 | The Harris corner detection algorithm computes a \$ 2 \times 2 \$ matrix at each el based on the first derivatives at that point and then computes the two eigenvalues of the matrix. Explain how you can use the two eigenvalues to label each pixel as a locally smoothed region, an edge point, or a corner point. |
| 22 | Assuming feature points have been previously detected using the SIFT feature detector, briefly describe the main steps of creating the SIFT feature descriptor at a given feature point. |
| 23 | Name three scene or image changes that the SIFT descriptor is invariant to. |
| 24 | Explain the changes SIFT descriptor is robust to. Is it invariant to major viewpoint changes as well? |




---

### 4. Image Derivatives and Edge Detection

| No. | Question |
| :-- | :-- |
| 25 | Explain how an approximation to the first derivative of an image can be obtained by convolving the image with the kernel [1 -1] for the image strip specified below: <br> [56 64 79 98 115 126 132 133] |
| 26 | Indicate where edges would be detected in the result of the above and state why. |


---

### 5. Motion, Tracking, and Optical Flow

| No. | Question |
| :-- | :-- |
| 27 | Define object tracking in the context of Computer Vision. |
| 28 | State and discuss the two main components of an object tracking algorithm. |
| 29 | In difference images, pixel values greater than zero (or greater than a certain threshold) are thought to reflect moving objects in the scene. However, this does not always have to be the case. There are other factors besides object motion that can cause non-zero values in a difference image. List three such factors. |
| 30 | Explain a method that can be used to estimate optical flow regardless of the magnitude of motion vectors. |
| 31 | Differentiate between motion detection and moving object detection. |
| 32 | What are the two main assumptions used in optical flow calculation? |
| 33 | Name three differential methods for optical flow estimation that are found in literature. |
| 34 | Briefly explain the idea of tracking with dynamics. |
| 35 | Name a motion model that is based on a predictor-corrector mechanism. |


---

### 6. System Design and Applications

| No. | Question |
| :-- | :-- |
| 36 | For each part below, design a system that would achieve the expected outcomes using computer vision algorithms and briefly explain the components of your system. Use flow diagrams to indicate the system components. Briefly outline an algorithm for each system. State any assumptions you make. <br> a) A driver assistant system equipped with a method to monitor how alert a car driver is and indicates when he/she is about to fall asleep. <br> b) A vision system to automatically monitor the speed limit for a vehicle by “reading" any speed limit signs which are passed by the car. |
| 37 | An office environment needs an automated "office assistant" that would take voice commands from a given location and reach a designated location to deliver items. Obstacles on the way need to be avoided as it moves within the environment. |
| 38 | You are assigned the task of developing a vision system for driver assistance. The system should warn a human driver when in danger of colliding with a pedestrian. The system should work during day and night, and also in poor weather conditions such as heavy rain. |
| 39 | You need to sort your holiday photographs and find photos which you are in. Describe a fully automatic algorithm that finds the subset of the images that contains un-occluded frontal faces of you. |
| 40 | At supermarkets, customers can generally choose individual pieces of items like fruits and vegetables. Propose a system to automatically identify the product so that the job of the human checker can be simplified. |
| 41 | Suggest a system that can be used to turn the headlights of a vehicle according to the bend angle to make driving at night more easy and safe. |


---

### 7. Skin Detection and Hybrid Images (Sample Paper)

| No. | Question |
| :-- | :-- |
| 42 | Assume you are assigned the task of devising a simple skin colour detector for a variety of photographs of people. <br> a) List the steps you would follow with a justification for each step. <br> b) How sensitive is your algorithm to color balance (scene lighting)? |
| 43 | Hybrid images are generated by superimposing two images at two different spatial scales. <br> a) Given a set of sample images, explain the steps to obtain hybrid images. <br> b) Suggest three applications where hybrid images can be used. |


---

## Key Mathematical Formulas \& Matrices

**Harris Matrix:**

$$
M = \begin{bmatrix}
I_x^2 & I_x I_y \\
I_x I_y & I_y^2
\end{bmatrix}
$$

**Harris Response:**

$$
R = \lambda_1 \lambda_2 - k(\lambda_1 + \lambda_2)^2
$$

**Edge Detection Kernel:**

$$
\text{Kernel} = [1\ -1]
$$

---

This list covers all unique questions, including those involving tables, matrices, and mathematical formulas, as extracted from the provided exam papers[^1][^2][^3][^4][^5].

<div style="text-align: center">⁂</div>

[^1]: CS408_2018_19_END.pdf

[^2]: CS408_2016_17_END.pdf

[^3]: CS408_2017_18_END.pdf

[^4]: CS408_2019_20_END.pdf

[^5]: Sample-paper.pdf

