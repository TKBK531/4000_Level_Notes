### Question 1

#### What is the main difference between clustering and classification?

- **Clustering** is **unsupervised** learning: it groups data based on similarity without predefined labels.
    
- **Classification** is **supervised** learning: it assigns labels to data based on a training set with known categories.
    

---

#### How can the clustering quality of any partition of the data be measured?

1. **Internal Measures** (no external labels):
    
    - **Silhouette Score**: Combines cohesion and separation.
        
    - **Dunn Index**: Ratio of minimum inter-cluster distance to maximum intra-cluster distance.
        
2. **External Measures** (using ground truth):
    
    - **Adjusted Rand Index (ARI)**
        
    - **Normalized Mutual Information (NMI)**
        

---

#### Challenges in selecting a clustering algorithm

- **How to define a cluster?**  
    Clusters can be defined based on density, distance, or statistical similarity—choosing the wrong definition may lead to meaningless groupings.
    
- **What features should be used?**  
    Irrelevant or highly correlated features can mislead clustering algorithms, so careful feature selection or dimensionality reduction is essential.
    
- **Should the data be normalized?**  
    Differences in scale can distort distance measures; normalization is often required for algorithms like K-Means.
    
- **Does the data contain any outliers?**  
    Outliers can heavily affect centroid-based methods, leading to inaccurate clusters.
    
- **How do we define the pair-wise similarity?**  
    The choice of distance metric (e.g., Euclidean, cosine) significantly influences cluster formation and must align with the data type.
    
- **How many clusters are present in the data?**  
    Most algorithms require this as input (e.g., K in K-Means), but the true number is often unknown and must be estimated.
    
- **Which clustering method should be used?**  
    The choice depends on data shape, scale, and distribution—no one method fits all scenarios.
    
- **Does the data have any clustering tendency?**  
    Some datasets may not contain any meaningful clusters; using clustering in such cases can lead to misleading results.
    
- **Are the discovered clusters and partition valid?**  
    Cluster validation is non-trivial and often requires internal, external, or visual validation techniques to assess quality.

---

- **No Universal Best:** Optimal choice depends on data/problem.
- **Optimal K (Number of Clusters):** Often unknown, hard to determine.
- **Data Assumptions:** Algorithms assume specific cluster shapes, densities, or scales.
- **High-Dimensionality:** Distances become less meaningful in many dimensions.
- **Scalability:** Some algorithms don't handle very large datasets well.
- **Interpretability:** Understanding and validating clusters can be difficult.

- **Core Measure:** Quantifies how "similar" or "dissimilar" two data points are.
- **Forms Clusters:** Algorithms group points with smaller distances (higher similarity).
- **Impacts Cluster Shape:** Different distance metrics (Euclidean, Manhattan, Cosine) lead to different cluster geometries.



#### Discuss the major challenges associated with selecting a clustering algorithm and elaborate on the use of distance as a pair-wise similarity measure. 

Distance measures quantify how similar or dissimilar two data points are:
- **Euclidean Distance**: Most common; suitable for continuous, normalized data.
- **Manhattan Distance**: Useful when movement is restricted to grid-like paths.
- **Cosine Similarity**: Often used in text data; measures angle between vectors rather than magnitude.
- **Mahalanobis Distance**: Takes data distribution into account.

**Challenges with Distance Measures**:
- Choice of distance metric affects clustering results.
- Requires feature scaling.
- May lose meaning in high dimensions.

---

#### Briefly describe how k-means algorithm works and list its strengths and weaknesses.

K-means is an **unsupervised machine learning algorithm** used for **clustering** data into a specified number of groups (**k**). Here's how it works:

1. **Initialization**: Select _k_ initial centroids randomly.
2. **Assignment Step**: Assign each data point to the nearest centroid (using Euclidean distance).
3. **Update Step**: Recalculate centroids as the mean of all points assigned to each cluster.
4. **Repeat**: Continue steps 2 and 3 until convergence (centroids no longer change significantly or a set number of iterations is reached).

---

**Strengths of K-means:**
- **Simple and easy to implement**
- **Fast and scalable** to large datasets
- Works well with **spherical, evenly sized clusters**
- Efficient in **low-dimensional spaces**

---

**Weaknesses of K-means:**
- Requires choosing the number of clusters **k** in advance
- **Sensitive to initial centroids** (can converge to local minima)
- **Not effective for non-spherical or varying-size clusters**    
- **Sensitive to outliers** and noisy data
---

#### When applying the k-means clustering algorithm for a given set of data points, if different starting positions were used for the centers in separate instances, will the algorithm always converge to the same solution? Explain your answer.
**No, the k-means algorithm will not always converge to the same solution** if different starting positions for the cluster centers are used.
##### Why:
K-means is **sensitive to the initial placement of centroids**. Since the algorithm uses a greedy approach to minimize within-cluster variance, it can get stuck in **local minima** depending on the starting positions. As a result, different initializations can lead to **different final clusters**.
##### Solution:
To address this, it's common to run the algorithm multiple times with different initializations (e.g., **k-means++** initialization) and select the best clustering result based on the **lowest total within-cluster sum of squares (WCSS)**.

#### K-means Example with City Block Distance

**Initial centers**: A1(2,10), A4(5,8), A7(1,2)

|Point|Distance to A1|Distance to A4|Distance to A7|Cluster|
|---|---|---|---|---|
|A1(2,10)|0|5|9|1|
|A2(2,5)|5|6|4|3|
|A3(8,4)|12|7|9|2|
|A4(5,8)|5|0|10|2|
|A5(7,5)|10|5|9|2|
|A6(6,4)|10|6|7|2|
|A7(1,2)|9|10|0|3|
|A8(4,9)|3|2|10|2|

**Clusters after assignment**:

- Cluster 1: A1
    
- Cluster 2: A3, A4, A5, A6, A8
    
- Cluster 3: A2, A7
    

**New centroids**:

- Cluster 1: (2,10)
    
- Cluster 2: ((8+5+7+6+4)/5, (4+8+5+4+9)/5) = (6, 6)
    
- Cluster 3: ((2+1)/2, (5+2)/2) = (1.5, 3.5)
    

---

#### Invariance to displacement and scale:

- **Method**: Normalize the data (e.g., subtract the mean to center it, then divide by standard deviation or use min-max scaling).
    
- **Effect**: Removes displacement (mean) and scales all features uniformly.
    
- **Limitation**: Works well for linear features but may not be effective if the structure of the clusters changes non-linearly with scale or location.
    

---

#### Invariance to rotation:

- **Method**: Use rotation-invariant features (e.g., principal component analysis (PCA) to align data) or use clustering algorithms based on distance measures invariant to rotation (like spectral clustering).
    
- **Effect**: Aligns data along principal axes, reducing sensitivity to orientation.
    
- **Limitation**: PCA may not preserve cluster separability; effectiveness depends on data geometry.
---

#### Hierarchical vs K-means Clustering

|Aspect|**Hierarchical Clustering**|**K-means Clustering**|
|---|---|---|
|**Approach**|Builds a hierarchy of clusters (bottom-up or top-down)|Partitional: divides data into _k_ non-overlapping clusters|
|**Number of Clusters**|Not required in advance (can be chosen after dendrogram)|Must specify _k_ beforehand|
|**Output**|Dendrogram (tree-like structure showing cluster relationships)|Final cluster centroids and assignments|
|**Deterministic?**|Yes (if distance metric and linkage are fixed)|No (results vary with initial centroids)|
|**Scalability**|Computationally expensive (O(n²) or worse)|Efficient and scalable (linear in number of points and clusters)|
|**Cluster Shape**|Can capture complex structures and nested clusters|Prefers spherical, equal-sized clusters|
|**Flexibility**|Supports various linkage methods and distance metrics|Limited by distance metric (usually Euclidean)|
|**Memory Usage**|Higher (due to distance matrix storage)|Lower (no distance matrix needed)|

**In summary**:

- **Hierarchical clustering** is better for smaller datasets and exploring nested cluster structures.
- **K-means** is more suitable for large datasets where speed and scalability are important.

---

#### Use of Euclidean distance in clustering

- Calculates straight-line distance.
    
- Assumes isotropic, convex clusters.
    
- Sensitive to scaling; features must be normalized.
    

---


#### “Automatically determining the number of clusters has been one of the most difficult problems in data clustering,” comments on the statement

- **True**. It's challenging because:
    
    - No universal metric.
    - Real-world data often doesn't separate cleanly.
    - Solutions include **Elbow method**, **Silhouette analysis**, **Gap statistic**, but they aren't always definitive.

---





### Question 2

#### How SVM Works

SVM is a **supervised learning algorithm** used for **classification** (and sometimes regression).

- It works by finding the **optimal hyperplane** that best separates data points of different classes.
- The goal is to **maximize the margin**, i.e., the distance between the hyperplane and the **nearest data points** from each class (called **support vectors**).
- For non-linearly separable data, SVM uses **kernel functions** (e.g., polynomial, RBF) to map data into a higher-dimensional space where a linear separator can be found.
    

#### SVM with XOR (non-linearly separable data)
|x₁|x₂|Label|
|---|---|---|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|0|
In 2D space, this is **not linearly separable** — no straight line can separate class 0 and class 1.

##### 🔹 Idea Behind the Kernel Trick:
Instead of manually mapping input to higher dimensions, the **kernel trick** allows SVM to compute dot products in a high-dimensional space **without explicitly transforming the data**.

Let’s define a **feature mapping** that mimics this (for intuition):

$\phi(x_1, x_2) = (x_1, x_2, x_1x_2)$

Then the transformed data becomes:

| x₁  | x₂  | x₁·x₂ | Label |
| --- | --- | ----- | ----- |
| 0   | 0   | 0     | 0     |
| 0   | 1   | 0     | 1     |
| 1   | 0   | 0     | 1     |
| 1   | 1   | 1     | 0     |

Now in **3D space**:
- Points with label 1 are at (0,1,0) and (1,0,0)    
- Points with label 0 are at (0,0,0) and (1,1,1)

These **are linearly separable in 3D**, and SVM can now find a separating hyperplane.



---


#### When your data is imbalanced, is SVM a good approach? Explain.
SVM is **not ideal by default** for imbalanced data because it tends to favor the majority class, leading to poor performance on the minority class. However, it can still work well if you:

- **Use class weights** (e.g., `class_weight='balanced'`)
- **Apply resampling techniques** (like oversampling the minority class)
- **Evaluate with proper metrics** (e.g., precision, recall, F1-score)

With these adjustments, SVM can handle imbalanced data effectively.


#### Consider the following training data from the categories: 
 #### $\omega_1: (1,1)^T, (2,2)^T, (2,0)^T$ 
 #### $\omega_2: (0,0)^T, (1,0)^T, (0,1)^T$
 #### Plot the six training points and construct by inspection the weight vector for the optimal hyperplane and the optimal margin. 
##### Step 1: Plot the points
- **ω₁** points (class 1):
    - (1,1), (2,2), (2,0)
- **ω₂** points (class 2):
    - (0,0), (1,0), (0,1)
These two classes are **linearly separable**.

##### Step 2: By inspection – draw optimal separating hyperplane
- You can see that the classes are separated along a diagonal.
- The **line $x + y = 1.5$** is a good candidate, as it:
    - Lies between (1,1) from ω₁ and (0,1), (1,0) from ω₂.
    - Separates the two classes without misclassification.

##### Step 3: Construct weight vector and bias
The general form of a hyperplane:
$w^T x + b = 0$

If the line is $x + y = 1.5$, then:
- $w = (1, 1)^T$
- So:
    $w^T x = x + y = 1.5 \Rightarrow b = -1.5$

Thus, the **optimal hyperplane** is:

$w = \begin{bmatrix}1\\1\end{bmatrix},\quad b = -1.5$

The **decision function** is:

$f(x) = w^T x + b = x + y - 1.5$

 #### What are the support vectors?
 Support vectors lie **closest to the hyperplane**, i.e., those for which:
$w^T x + b = \pm1$

Let's compute $w^T x + b$ for each point:

##### Class ω₁:
- $(1,1): 1 + 1 - 1.5 = 0.5$
- $(2,2): 2 + 2 - 1.5 = 2.5$
- $(2,0): 2 + 0 - 1.5 = 0.5$
##### Class ω₂:
- $(0,0): 0 + 0 - 1.5 = -1.5$
- $(1,0): 1 + 0 - 1.5 = -0.5$
- $(0,1): 0 + 1 - 1.5 = -0.5$

The points **closest** to the margin (where $f(x) = \pm1$) are:
- **(1,1)** from ω₁: $f(x) = 0.5$
- **(2,0)** from ω₁: $f(x) = 0.5$
- **(1,0)** and **(0,1)** from ω₂: $f(x) = -0.5$

These are **not exactly on the margin** (±1), but in SVM, we treat the closest points as support vectors.

So by inspection, the **support vectors** are:

$((1,1),\ (2,0)\ \text{from } \omega_1,\quad \text{and } (1,0),\ (0,1)\ \text{from } \omega_2$




### Question 3

#### Steps of Harris Corner Detection
Here are the **main steps of the Harris Corner Detector**:

1. **Convert image to grayscale** (if not already).
2. **Compute image gradients**:
    - Use Sobel operators to compute gradients in the x and y directions:
	    $I_x$​ and $I_y$​.
3. **Compute products of gradients**:
    - $I_x^2, I_y^2, I_x I_y$​

4. **Apply Gaussian filter** to smooth the gradient products:    
    - $S_{xx} = G * I_x^2$
    - $S_{yy} = G * I_y^2$
    - $S_{xy} = G * I_x I_y$
5. **Form the structure matrix (M)** at each pixel:
  $M = \begin{bmatrix} S_{xx} & S_{xy} \\ S_{xy} & S_{yy} \end{bmatrix}$
  
6. **Compute the Harris response (R)**:
    $R = \text{det}(M) - k \cdot (\text{trace}(M))^2$
    where $k$ is a sensitivity parameter (typically $0.04 \leq k \leq 0.06$)
7. **Threshold the response R** to find corner candidates.
8. **Apply non-maximum suppression** to refine corner locations.

#### Are Harris Corners rotation invariant?
Yes, **Harris corners are invariant to rotation**.

**Why?**  
The Harris detector uses the **eigenvalues of the structure matrix**, which depend on **intensity changes** in all directions around a point. These eigenvalues—and the resulting corner response—remain the same even if the image is rotated.

So, the detector can still identify the **same corners** after rotation, making it **rotation-invariant**.  

---

#### SIFT Descriptor Steps

1. **Scale-space extrema detection**:
    - Detect keypoints by finding local maxima/minima in **Difference of Gaussians (DoG)** across multiple scales.
	
2. **Keypoint localization**:
    - Refine keypoint positions by fitting a 3D quadratic function to remove low-contrast or poorly localized points.
    
3. **Orientation assignment**:
    - Assign one or more dominant **orientations** to each keypoint based on local gradient directions, making the descriptor **rotation-invariant**.

4. **Descriptor generation**:    
    - Around each keypoint, compute **gradient magnitudes and orientations** in a local 16×16 region.
    - Divide it into **4×4 subregions** and build an **8-bin orientation histogram** for each, resulting in a **128-dimensional vector**.


This descriptor is **robust to scale, rotation, and moderate affine changes**.

#### SIFT Invariance

- Scale
    
- Rotation
    
- Illumination (partially)
    
- Affine distortion (partially)
    

---

#### Good vs Bad Features
A **good feature** is one that is **distinctive, repeatable, and robust** under various conditions. Here's a brief explanation:

##### ✅ Good Feature:
- **Distinctive**: Clearly different from surrounding pixels (e.g., corners, blobs).
- **Repeatable**: Can be reliably detected under **scale, rotation, illumination**, and **viewpoint changes**.
- **Stable**: Consistently detected across similar images or frames.
- **Well-localized**: Accurately positioned in the image.
    
##### ❌ Bad Feature:
- **Low contrast** or **flat regions** (e.g., uniform textures) — hard to detect or match.
- **Edges only** — not unique in one direction, leading to ambiguity.
- **Not repeatable** — disappears under slight changes in viewpoint or lighting.

In short:  
**Good features** are **unique and reliable** for matching; **bad features** are **ambiguous and unstable**.

#### Are corners better than edges?
Yes, **corners are considered better than edges** for feature detection.
##### Why?
- Corners have **variation in intensity in both directions**, making them **more distinctive**.
- **Edges vary in only one direction**, so matching them can be **ambiguous** (e.g., along the edge line).
- Corners are more **repeatable and robust** under transformations (e.g., rotation, scale).

*In brief:*  
**Corners are better** because they provide **unique, stable points** that are easier to detect and match accurately.

---

### Question 4

#### Motion detection vs Moving object detection

- **Motion Detection**:  
    Detects **any change in pixels** over time — it signals that **something is moving**, but doesn’t identify what.
- **Moving Object Detection**:  
    Goes further by detecting **and localizing the actual object** that is moving (e.g., person, car) — often involves background subtraction, object segmentation, or tracking.
    
**In short**:
- **Motion detection** = detects _that_ motion happened.
- **Moving object detection** = detects _what_ is moving and _where_.
    

---

#### Object tracking (Computer Vision)
**Object tracking** in computer vision is the process of **locating and following a specific object** across a sequence of video frames **over time**.

It involves:
- **Identifying the object** in the initial frame.
- **Predicting its position** in subsequent frames.
- **Updating the object's location** even with changes in motion, scale, lighting, or partial occlusion.

In short:  
**Object tracking** continuously monitors a target object's movement through video frames after it has been initially detected.
#### Main components of tracking algorithm
The two main components of an object tracking algorithm are:

1. **Object Detection (Initialization):**  
    Identify and locate the object of interest in the first frame or whenever tracking starts.    
2. **Object Tracking (Prediction & Update):**  
    Continuously predict the object's new position in subsequent frames and update the tracking based on new observations.


In brief:  
**Detect the object first, then track its movement frame-by-frame.**

---

#### Optical flow assumptions
- ##### Brightness Constancy:  
    The pixel intensity of a point remains constant between consecutive frames.  
    _Why?_ Because optical flow tracks how the same point moves, assuming its brightness doesn’t change helps link pixels across frames.
- ##### Spatial Coherence (Smoothness):  
    Neighboring pixels have similar motion (velocity).  
    _Why?_ Real-world motions are usually smooth over small regions, so assuming smooth flow helps solve the otherwise under-constrained problem.
- ##### Small Motion:  
    The displacement of pixels between frames is small.  
    _Why?_ Optical flow equations are derived using a linear approximation (Taylor series), which is valid only for small movements.

---

#### Differential methods for optical flow

**Differential methods** for optical flow estimation use the **spatial and temporal derivatives** of image intensity to calculate motion. The main idea is based on the **brightness constancy assumption** and small motion.

##### Brief explanation:
- Use the **optical flow constraint equation**:
    $I_x u + I_y v + I_t = 0$
    where $I_x, I_y$​ are spatial intensity gradients, $I_t$​ is temporal gradient, and $u, v$ are the optical flow components (velocity in x and y).
- Since this gives **one equation with two unknowns $(u,v)$**, additional constraints are needed:
    - **Lucas-Kanade method**: Assumes flow is constant in a small neighborhood and solves for u,vu,vu,v using least squares.
    - **Horn-Schunck method**: Adds a global smoothness constraint to enforce spatial coherence of flow.        

In summary, differential methods estimate optical flow by computing intensity derivatives and solving equations under assumptions of brightness constancy and motion smoothness.

---

#### Tracking with dynamics
**Tracking with dynamics** means incorporating a **motion model** that predicts how an object moves over time to improve tracking accuracy.
##### The idea:
- Instead of just detecting the object's position frame-by-frame, the tracker **uses past states** (position, velocity, acceleration) to **predict where the object will be next**.
- This prediction guides the search for the object in the new frame, making tracking more robust to occlusions, noise, or fast movements.
- Common tools include **Kalman filters**, **Particle filters**, or other Bayesian methods that combine prediction (dynamics) with observations.

**In brief:**  
Tracking with dynamics uses the object's motion behavior to anticipate its future location, enabling smoother and more reliable tracking over time.

---

#### A motion model that is based on a predictor-corrector mechanism

A **predictor-corrector motion model** works in two steps:
1. **Predictor step:**  
    Uses the object's current state (position, velocity) and a motion model (e.g., constant velocity) to **predict the next state** (where the object is expected to be).
2. **Corrector step:**  
    Updates the prediction by **incorporating the actual measurement** (detected object position) to correct errors and refine the estimate.

This approach is commonly used in **Kalman filters**, balancing prediction and observation for accurate tracking.

**In short:**  
Predict where the object should be, then correct that prediction using new observations.

---

#### Explain a model that can be used to estimate optical flow regardless of the magnitude of motion vectors

A model that can estimate optical flow regardless of motion magnitude is the **Pyramidal Lucas-Kanade method**.
##### Brief explanation:
- It builds an **image pyramid**—multiple scaled versions of the image (from coarse to fine).
- Starts estimating flow at the **coarsest (lowest resolution) level**, where large motions appear smaller and easier to handle.
- Then **refines the flow estimates progressively at finer levels**, adjusting for details and larger motions.

This **multi-scale approach** overcomes the small-motion limitation of basic differential methods and can handle large motion vectors effectively.

**In short:**  
Use a **coarse-to-fine pyramidal scheme** to estimate optical flow for both small and large motions.


### Question 5


## 1. Driver Alertness Monitoring System

**Goal:** Detect driver drowsiness and alert when sleepiness is imminent.

### Components

- **Video Capture:** Camera focused on driver’s face.
- **Face and Eye Detection:** Use Haar cascades or SIFT/Harris features with classifiers to detect face and eyes.
- **Eye State Analysis:** Detect eye openness using skin color detection and thresholding or simple feature descriptors.
- **Blink Rate and Eye Closure Duration Estimation:** Track eye closure over time.
- **Alert Module:** Trigger alarm if eyes remain closed beyond threshold.


### Algorithm Outline

1. Capture video frames continuously.
2. Detect face region using Haar cascades or feature matching.
3. Detect eyes within face using skin color segmentation and corner detection.
4. Analyze eye state (open/closed) by thresholding eye region intensity or texture features.
5. Calculate blink rate and duration of eye closure.
6. If eye closure duration exceeds predefined threshold, trigger alert.

### Assumptions

- Good lighting conditions in the vehicle cabin.
- Camera positioned to capture driver’s face clearly.
- Basic image processing techniques (filters, thresholding) are available.

---

## 2. Automatic Speed Limit Sign Recognition System

**Goal:** Detect and read speed limit signs from a moving vehicle.

### Components

- **Video Capture:** Forward-facing camera.
- **Sign Detection:** Use color segmentation (red circle) and shape detection (circle detection via Hough transform).
- **Character Recognition:** Extract digits inside the sign using SIFT features and SVM classifier trained on digit images.
- **Speed Limit Display:** Overlay recognized speed limit on the dashboard.


### Algorithm Outline

1. Capture video frames.
2. Apply color thresholding to detect red circular regions.
3. Use shape detection to confirm circular signs.
4. Extract sign region and preprocess (grayscale, resize).
5. Detect keypoints using SIFT; extract descriptors.
6. Classify digits inside sign using trained SVM on SIFT descriptors.
7. Display recognized speed limit.

### Assumptions

- Signs are visible and not occluded.
- Pretrained SVM classifier for digits is available.
- Reasonable lighting conditions.

---

## 3. Automated Office Assistant Robot Vision System

**Goal:** Navigate office environment, recognize voice command location, and avoid obstacles.

### Components

- **Voice Command Localization:** Microphone array or fixed location assumed.
- **Obstacle Detection:** Use motion detection (frame differencing or optical flow) and depth sensing (if available).
- **Path Planning:** Use k-means clustering to segment free space and obstacles.
- **Navigation:** Track features with SIFT/Harris for localization.


### Algorithm Outline

1. Receive voice command from fixed location.
2. Use camera to scan environment; detect obstacles via background subtraction.
3. Segment scene using k-means clustering to identify free paths.
4. Track environment features with SIFT for localization.
5. Plan path avoiding obstacles and move to target.

### Assumptions

- Voice command location is known.
- Environment is reasonably static.
- Robot has basic movement control.

---

## 4. Automatic Product Identification on Scale

**Goal:** Identify fruits/vegetables placed on scale automatically.

### Components

- **Image Capture:** Camera above scale.
- **Product Segmentation:** Use color-based skin detection adapted for fruit/vegetable colors.
- **Feature Extraction:** Extract SIFT features from segmented product.
- **Classification:** Use SVM trained on product features.
- **Weight Measurement:** Scale sensor input.


### Algorithm Outline

1. Capture image of product on scale.
2. Segment product using color thresholding (similar to skin detection).
3. Extract keypoints and descriptors using SIFT.
4. Classify product type using trained SVM classifier.
5. Combine product ID with weight from scale.

### Assumptions

- Products are visually distinct.
- Pretrained SVM model available.
- Controlled lighting on scale.

---

## 5. Adaptive Headlight Control System

**Goal:** Adjust vehicle headlights to illuminate road curves.

### Components

- **Video Capture:** Forward-facing camera.
- **Road Curve Detection:** Use optical flow or lane detection via edge detection and Hough transform.
- **Curve Angle Estimation:** Calculate steering angle from lane curvature.
- **Headlight Control:** Adjust headlight direction based on curve angle.


### Algorithm Outline

1. Capture video frames.
2. Detect lane markings using edge detection and Hough transform.
3. Estimate road curvature and steering angle.
4. Use optical flow to confirm motion direction.
5. Adjust headlight angle proportionally to curve angle.

### Assumptions

- Lane markings are visible.
- Vehicle speed and steering angle sensors available for integration.
- Basic image filtering and edge detection available.

---

## 6. Pedestrian Collision Warning System

**Goal:** Warn driver of potential pedestrian collisions day/night and in poor weather.

### Components

- **Video Capture:** Infrared and visible spectrum cameras (if available).
- **Pedestrian Detection:** Use SIFT features and SVM classifier trained on pedestrian images.
- **Motion Detection:** Optical flow to detect moving objects.
- **Distance Estimation:** Use size and position in frame.
- **Warning Module:** Alert driver when pedestrian is too close.


### Algorithm Outline

1. Capture frames from visible and infrared cameras.
2. Detect pedestrians using SIFT feature extraction and SVM classification.
3. Track detected pedestrians using optical flow.
4. Estimate distance using bounding box size or stereo vision (if available).
5. If pedestrian within danger zone, trigger warning.

### Assumptions

- Availability of infrared camera improves night detection.
- Pretrained pedestrian SVM classifier available.
- Moderate occlusion and weather conditions.

---

## 7. Automatic Face Photo Sorting

**Goal:** Find photos containing unoccluded frontal faces of a specific person.

### Components

- **Face Detection:** Use Haar cascades or skin color segmentation combined with Harris corner detection.
- **Face Recognition:** Use SIFT descriptors matched against reference images of the person.
- **Occlusion Handling:** Discard faces with insufficient feature matches.


### Algorithm Outline

1. For each photo, detect faces using Haar cascades or skin color segmentation.
2. Extract SIFT features from detected faces.
3. Match features with reference images of the person using descriptor matching.
4. If sufficient matches found and face is frontal (based on feature distribution), include photo in subset.

### Assumptions

- Reference images of the person are available.
- Faces are mostly frontal and well-lit.
- Occlusions reduce feature matches below threshold.

---

## 8. Simple Skin Color Detector

### Steps and Justifications

1. **Collect Diverse Images:** To cover various skin tones and lighting conditions.
2. **Convert to Chromaticity Space:** Normalize RGB to remove intensity effects.
3. **Label Skin Pixels:** Manually mark skin regions to build color distribution.
4. **Model Skin Color Distribution:** Use Gaussian model or mean and covariance.
5. **Classify Pixels:** Use Mahalanobis distance or thresholding to detect skin.
6. **Post-processing:** Morphological operations to clean up detection.

### Sensitivity to Color Balance

- The algorithm is sensitive to lighting changes because chromaticity depends on scene illumination.
- Adaptive thresholding or illumination normalization can improve robustness.
- Simpler color ratios work but less accurate than full statistical models.

---

## 9. Hybrid Image Generation

### Steps to Obtain Hybrid Images

1. **Select and Align Images:** Choose two images with similar content and align key features.
2. **Apply Low-Pass Filter:** Blur one image using Gaussian filter to extract low frequencies.
3. **Apply High-Pass Filter:** Subtract blurred version from original on second image to get high frequencies.
4. **Combine Images:** Add low-frequency and high-frequency images to create hybrid.
5. **Adjust Weights:** Tune contribution of each image for best perceptual effect.

### Applications

- **Face Expression Change:** Create images that change expression with viewing distance.
- **Scene Configuration Display:** Show two different scenes in one image depending on distance.
- **Texture Display:** Present textures that appear or disappear based on viewing distance.

---

This outline uses methods and algorithms covered in your course, leveraging image filtering, feature detection (SIFT, Harris), machine learning (SVM, k-means), and motion analysis (optical flow, frame differencing). Each system is designed with practical assumptions and straightforward steps suitable for implementation with your current knowledge.



