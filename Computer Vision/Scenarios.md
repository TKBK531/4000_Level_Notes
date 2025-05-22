#### 1. A driver assistant system equipped with a method to monitor how alert a car driver is and indicates when he/she is about to fall asleep.

##### 🧠 System Overview

The system uses **face and eye tracking** via a dashboard-mounted camera to monitor:
- Eye closure duration (PERCLOS)
- Yawning
- Head posture

It triggers an alert (sound/vibration) when drowsiness is detected.

---

##### 📊 Flow Diagram

```

+---------------------+
|  Camera Input (RGB) |
+---------+-----------+
          |
          v
+----------------------+
|  Face Detection      |
+---------+------------+
          |
          v
+----------------------+
|  Eye & Mouth Region  |
|  Detection           |
+---------+------------+
          |
          v
+----------------------------+
|  Eye Aspect Ratio (EAR)   |
|  & Mouth Aspect Ratio     |
|  (MAR) Computation        |
+---------+------------------+
          |
          v
+-----------------------------+
| Drowsiness Detection Logic |
| (EAR < threshold for t sec |
|  OR MAR high = yawning)    |
+---------+-------------------+
          |
          v
+-------------------+
| Issue Alert (e.g.,|
| Buzzer/Display)   |
+-------------------+


```


---

##### ⚙️ Algorithm Outline
 *Assumptions*:
- A forward-facing camera is mounted on the dashboard.
- Good lighting or IR camera for night operation.
- Real-time processing at least 10 fps.
    

 ***Algorithm Steps:***
1. **Initialize camera feed.**
2. **Detect the face** using a face detector (e.g., Haar cascades, Dlib HOG, or a CNN).
3. **Detect facial landmarks** (e.g., using Dlib’s 68-point model).
4. **Extract eye and mouth landmarks**.
5. **Calculate Eye Aspect Ratio (EAR):**

$$
    EAR = \frac{||p_2 - p_6|| + ||p_3 - p_5||}{2 \times ||p_1 - p_4||}
$$
6. **Calculate Mouth Aspect Ratio (MAR)** similarly to detect yawning.
7. If:
    - **EAR < threshold (e.g., 0.25)** for more than a set duration (e.g., 2 seconds), or
    - **MAR > yawning threshold**
8. Then:
    - Trigger an **alert** (buzzer/screen warning).
9. Loop back to Step 2 for continuous monitoring.

---

##### 🧪 Technologies and Libraries

|Task|Tool/Library|
|---|---|
|Face & landmark detection|Dlib, OpenCV, MediaPipe|
|Real-time video processing|OpenCV|
|Sound alert|`winsound` / buzzer hardware|
|ML alternative (optional)|Deep learning model (e.g., CNN + LSTM for fatigue prediction)|

---

##### ✅ Expected Outcomes

- Detect driver drowsiness **within seconds**.
- Alert system **activates early**, reducing accident risk.
- Can be extended with other sensors (steering input, heart rate) for robustness.