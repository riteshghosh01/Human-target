#   Introduction  #
A fast expanding area of computer vision, human action detection has uses in
many different sectors including video surveillance, sports analysis, healthcare
monitoring, and human-computer interaction. These systems can increase
automation, boost safety, and create new user experiences by identifying and
classifying human activities including walking, running, or standing.


Human action detection's complexity results from elements including variations
in body posture, occlusions, lighting conditions, and different camera angles.
Building a strong and precise detection system calls for sophisticated algorithms
able to handle such difficulties in actual situations.


This project aims to realize an implementation of a real-time human action
detection system based on the YOLOv8 object detection framework. Given its
accuracy and speed, we train a custom YOLOv8 model on a dataset which is
specifically tailored for three basic human actions: walking, standing, and
running. The goal is to design a scalable and effective system that can reliably
recognize and classify these actions within video streams.


With this project, we seek to prove the practical application of recent advances
in object detection for human action recognition and lay the groundwork for
further development on more complicated actions and larger datasets. The
system is intended to have lightweight components for real-time processing,
making it suitable for a multitude of practical implementations.


![image](https://github.com/user-attachments/assets/fc45b1b5-2837-4770-ac92-3d4da0efa308)


# Scope of the Project  #

The scope of this project encompasses the design, development, and deployment
of a real-time abnormal activity detection system using a custom-trained
YOLOv8 deep learning model, optimized for performance, generalizability, and
interpretability across a variety of real-world scenarios. The proposed system
aims to go beyond traditional surveillance methods by integrating intelligent,
context-aware, and visually interpretable mechanisms to monitor and respond
to abnormal human behavior in dynamic environments.


This project envisions a system that is not only capable of flagging anomalies in
dynamic environments—such as public spaces, healthcare facilities, or industrial
areas—but is also designed to function efficiently on standard hardware or edge
devices, reducing the need for high-end infrastructure or extensive retraining.
The detailed goals are outlined below:


## 1. Efficient Real-Time Processing:
   
 Low Latency: The system will prioritize real-time performance, ensuring
that abnormal activities are detected and flagged with minimal delay. This
is critical for time-sensitive applications such as live surveillance or
emergency response.

 Hardware Optimization: By utilizing YOLOv8's lightweight architecture,
the system will be designed to run efficiently on standard hardware,
including edge devices like Raspberry Pi, GPUs, or CPUs, without
compromising on speed or accuracy.

 High Throughput: The system will process multiple input streams (e.g.,
from CCTV cameras or drones) simultaneously, providing scalability for
large-scale deployments.


![image](https://github.com/user-attachments/assets/ce6037be-94f4-4197-b0b3-8df14d4c6f83)


## 2. Context-Aware Anomaly Identification:

Unlike conventional systems that only detect predefined actions, this project
introduces a behavior-driven anomaly detection approach.

 Spatial and Temporal Analysis: Tracks motion across multiple frames to
evaluate behavioral trends (e.g., someone standing in the same place too
long).

 Dynamic Crowd Awareness: Assesses crowd density and changes in
movement patterns to flag anomalies (e.g., a sudden rush or an individual
sprinting in a dense crowd).

 Proximity Detection: Identifies close grouping of individuals in sensitive
zones, potentially indicating a conflict or unauthorized gathering.

 Environment Sensitivity: Takes into account lighting, camera angle, and
crowd density to avoid false positives in variable conditions.


## 3. Data-Efficient Training and Generalization:

The system is built with efficiency in mind, particularly for real-world
deployment where data collection and annotation may be limited.

 Transfer Learning with YOLOv8: Utilizes pre-trained weights from COCO
dataset, then fine-tunes with a smaller, domain-specific Roboflow dataset
to specialize in human activities.

 Minimal Annotation Needs: Reduces the burden of creating vast labeled
datasets—abnormal behavior is inferred from context, not just labels.

 Data Augmentation: Enhances the training dataset with transformations
such as flipping, scaling, and lighting adjustments, improving performance
across diverse scenarios.

 Robust Generalization: Performs reliably across varied
environments—indoor/outdoor, day/night, crowded or sparse—without
needing re-training.


## 4. Explainable Output and Visual Feedback:

Transparency is key in surveillance systems. This project includes
interpretability tools that make the system's decisions clear and user-friendly.

 Bounding Boxes and Labels: Every detected individual is enclosed in a
box with activity labels (e.g., “walking”, “fighting”) and a confidence score.

 On-Screen Status Indicators: Abnormal behaviors are visually marked on
video feeds for real-time decision-making by operators.

 Heatmaps: A cumulative thermal map shows the zones with highest
activity or anomalies, helping in identifying hotspots or unusual
movements across time.

 Abnormal Frame Saving: Frames with detected anomalies are saved with
timestamps and activity types, creating a visual record for later reviews.


## 5. Automated Alerts and Intelligent Logging:

To support rapid response and post-incident review, the system incorporates
multi-modal alerting and event tracking.

 Audio Alerts: Beep tones are triggered when critical anomalies are
detected—each event type can be assigned a distinct sound pattern.

 Spam Control Mechanism: Alerts include cooldown timers to avoid
repeated beeping for continuous or overlapping events.

 Logging System: Abnormal activities are logged in a text file including:
o Timestamp
o Detected activity (e.g., “armed”, “loitering”)
o Location/frame info (optional in multi-camera setups)

 Audit-Ready Reports: The loggedpdata, combined with saved frames,
supports investigations, reporting, or ML retraining.


![image](https://github.com/user-attachments/assets/4b724bd6-4346-46e0-8343-e9775ddaa14f)


## 6. Scalable, Modular, and Cross-Domain Design

The architecture is built to be adaptable and extensible, meeting both small-scale
and enterprise-level needs across various sectors.

 Modular Implementation: New behaviors, rules, or detection targets can
be added without restructuring the whole system.

 Multi-Camera and Cloud Readiness: Scales from a single camera setup
(e.g., a retail shop) to large deployments (e.g., city-wide smart surveillance
networks).

 Integration with Existing Infrastructure: Can be plugged into existing
CCTV systems, IoT hubs, or cloud dashboards via standard interfaces.

 Wide-Ranging Applications:
o Public Safety: Detecting fights, thefts, suspicious loitering in stations,
streets, and airports.
o Healthcare: Monitoring for patientgfalls, fainting, or unauthorized
exits.
o Industrial Environments: Detecting safety breaches, accidents, or
restricted access in hazardous areas.
o Education and Retail: Identifying crowding, aggression, or
shoplifting in schools, malls, and shops.


# Input and Output  #

## Input:

The input to the abnormal activity detection system primarily consists of video
data obtained from live surveillance feeds or pre-recorded footage. These videos
may come from real-world environments such as public spaces, hospitals,
offices, or educational institutions. The goalhis to detect and classify human
actions within each frame in real time.

### Video Collection:

 Videos were collected from simulated environments or sourced from
surveillance systems.

 Scenarios included publiciplaces, indoor rooms, streets, and hallways
under varied lighting and density conditions.

### Custom Datasets:

To train the detection model, a custom dataset was developed using Roboflow, a
platform that simplifies the process of annotating and managing visual data.

 Video frames were extracted and manually labeled with specific action
classesglike walking, running, standing, fighting, sitting, jumping, lying
down, robbery, and armed.

 Once labeled, theldataset was exported in YOLO format and used to train
the YOLOv8s model in Google Colab.

 Roboflow also provided automated data augmentation to improve model
accuracy across varied conditions.


![image](https://github.com/user-attachments/assets/b7af9dc3-1181-41d4-b7d3-93acd693f438)


## Output:

The output of the system will consist of multiple actionable results for abnormal
activity detection:

###  Visual Detection and Annotation :

The system provides real-time visual feedback by identifying individuals in the
video frames and markinguthem with bounding boxes. Each detected action is
labeled with a corresponding tag like "Running", "Fighting", or "Robbery", and
each detection includes a confidence score indicating the system’s certainty. This
helps operators interpret situations instantly and with greater accuracy.

###  Anomaly Logging and Metadata:

In addition to visual outputs, the system maintains a structured log file that
records details such as the timestamp, detected action, frame number, and the
duration of the event. The log may alsojinclude contextual information like
estimated crowd density or predefined thresholds for specific areas, aiding
deeper analysis and better scene understanding.


![image](https://github.com/user-attachments/assets/5a99cb1c-69ef-45be-a205-564274321f4c)



###  Saved Annotated Frames:

Any frame in which an abnormal activity is detected is automatically saved in a
designated folder. Each file is timestamped and labeled with the type of anomaly,
making it easy to locate and review incidents later. The filenames follow a clear
format (e.g., fighting_12_05_2025_10_33_21.jpg) for traceability.

###  Abnormality Heatmap:

A heatmap is created based on areas with high motion or recurring abnormal
activities. This visual tool helps identify hotspots or zones that require increased
attention, and it can also guide future decisions about camera placement or
crowd control measures.

###  Real-Time Audio Alerts:

For high-risk actions like fights, armed threats, or robbery, the system triggers
distinct audio alerts. Each type of anomaly can have a unique tone, and a built-in
cooldown mechanism prevents the system from issuing repeated alerts for the
same event in quick succession.

###  Performance Metrics:

In addition to the visual outputs, the system will log performance metrics such
as precision, recall, F1-score, and accuracy based on the model’s ability to
correctly detect abnormal actions, which can be helpful for evaluating and fine-
tuning the system.


# Methodology Used #

The proposed system leverages a hybrid approach combining the object
detection strength of YOLOv8 with contextual and motion-based analysis using
OpenCV. The methodology is designed for real-time abnormal activity
detection and operates effectively on both live surveillance feeds and recorded
video streams. The system’s workflow consists of the following key components:

##  Dataset Preparation and Preprocessing:

To train the system effectively for abnormal activity detection, a custom dataset
was created using Roboflow, a platform designed for annotating and managing
image datasets. Video footage was converted into frames, capturing both normal
and abnormal human activities.

### o Classes:
Each frame was annotated with one of nine action classes:
Walking, Standing, Sitting, Running, Fighting, Jumping, Lying Down,
Robbery, and Armed.

### o Annotation Format:

- Bounding boxes were drawn around each person.
- Labels were assigned using YOLO annotation format (text files
containing object class, coordinates, and dimensions).

### o Data Augmentation:

To improve model generalizationkand reduce overfitting, Roboflow applied
several augmentation techniques like Horizontal flipping, brightness and
contrast variation, rotation and scaling and random cropping.


![image](https://github.com/user-attachments/assets/ca5afc49-5c60-438b-bedb-e4790ebe5e44)


### o Export Format:

The dataset was exported in YOLOv8-compatible format, including:
- Structured folder hierarchy (train/val/test)
- Corresponding .txt annotation files
- A data.yaml file containing class names and dataset paths.


![image](https://github.com/user-attachments/assets/a5e778e4-63e7-473a-872f-61a405c9026e)


##  Model Training Using YOLOv8:

Model training was conducted using the YOLOv8s (small) model in Google Colab
with GPU support, leveraging the Ultralytics framework.

o The training spanned 50 to 100 epochs, with a batch size of 16–32.

o Key performance metrics such as precision, recall, and mean Average
Precision (mAP@0.5 and mAP@0.5:0.95) were used to monitor progress.

o The model was validated using a separate split of the dataset, and the best-
performing weights were saved as best.pt for use in real-time detection.


![image](https://github.com/user-attachments/assets/c3eb5d53-0f1f-438d-a8ef-c6f07df54fb4)


##  Contextual Preprocessing and Background Subtraction:

To enable behavior-aware detection, the system processes environmental
context using background subtraction:

o MOG2 (Mixture of Gaussians) is applied to identify moving foreground
objects.

o Foreground masks are refined using morphological operations to reduce
noise.

o Crowd density is calculated by comparing motion pixels to total pixels. If
density exceeds pre-set thresholds (e.g.>20% during standing), the
activity is flagged as potentially abnormal.

##  Abnormal Motion and Temporal Analysis:

YOLOv8 identifies actions frame-by-frame, while OpenCV-based analysis
captures behavioral anomalies across time:

o Sudden movement detection tracks the displacement of bounding box
centers across consecutive frames. Large pixel shifts are interpreted as
abrupt or suspicious motion.

o Temporal standing analysis monitors individuals who remain stationary
beyond a defined duration (e.g., more than 10 seconds), flagging them as
potentially loitering or unwell.

These methods enrich object detection with time-aware behavior context,
improving abnormality detection without needing complex LSTM or 3D CNN
models.

##  Group Proximity and Interaction Analysis:

To detect potentially suspicious gatherings or social interactions:
o The system calculates pairwise distances between people using bounding
box center coordinates.

o If three or more individuals cluster within a fixed radius (e.g., 100 pixels),
the system marks it as a group event.

o Group proximity in sensitive areas (like near a bank counter or entrance) is
treated as an anomaly.

##  Alerting, Logging, and Visual Outputs:

To ensure usability and incident traceability, several output mechanisms are
implemented:

### o Auditory Alerts:

Abnormal actions like robbery, fighting, or armed threats trigger unique
beep tones using the winsound.Beep() function.

### o Logging:

All anomalies are recorded in a .txt file with timestamp and activity type.

### o Frame Capture:

Abnormal frames are saved automatically to a designated folder
(/abnormal_frames/) using filenames that include timestamps and action
labels.

### o Heatmap Generation:

Motion masks accumulated over time are converted into thermal-style
activity heatmaps using OpenCV's COLORMAP_JET, highlighting frequent
zones of movement or activity.

### o User-Friendly Dashboard:​

A dashboard interface may be developed to display live video feeds
alongside real-time analytics, providing operators with a centralized view
of activities.


![image](https://github.com/user-attachments/assets/3292d7bd-e877-487f-bff9-3d8675622d73)


# Key Advantages of the Methodology #

## 1. Real-Time Performance:

The combination of the YOLOv8s model with OpenCV-based tracking
allows the system to detect and analyze human activities instantly. This
makes it highly effective for live surveillance scenarios where quick
response is essential, such as detecting fights, robberies, or other
suspicious behavior.

## 2. Interpretability and Transparency:
Each detection is visually marked with bounding boxes and action labels,
while all abnormal activities are logged with timestamps. This clear and
interpretable output builds trust with end-users and facilitates accurate
post-event analysis.

## 3. Robustness Across Environments:

The methodology is designed to handle real-world challenges such as
variable lighting, complex backgrounds, and dynamic crowd densities.
Background subtraction, noise reduction, and contextual analysis help
maintain consistent performance even in difficult conditions.

## 4. Scalability for Large Deployments:

The system supports multiple video streams and modular integration,
making it suitable for both small installations (e.g., offices or clinics) and
larger infrastructures like airports, malls, or city-wide surveillance
networks.

## 5. Resource-Efficient Implementation:

By using a lightweight version of YOLOv8 and optimizing processes with
OpenCV, the system operates efficiently on standard hardware and even
edge devices. This minimizes computational load and makes the solution
cost-effective for a wide range of applications.

# Result #

The YOLOv8s-based abnormal activity detection system was evaluated on a
custom dataset comprising various human actions labeled via Roboflow. The
system's performance was assessed using precision, recall, F1-score, and
confusion matrix data, with visual output provided through confidence-based
curves.

##  Model Accuracy:

The system achieved a detection accuracy of approximately 72.6%,
correctly identifying both normal and abnormal human actions across
multiple classes.

##  Precision-Recall-F1 Performance:

The model demonstrated strong overall performance with a maximum
precision of 1.00, recall of 0.77, and an F1-score of 0.62 at a confidence
threshold of 0.585. Classes such as robbery, jumping, and sitting showed
particularly high scores across all metrics, while slightly lower recall was
observed in more visually complex classes like armed and fighting, likely
due to overlap and class imbalance.



![image](https://github.com/user-attachments/assets/5b2c33cf-bb32-42ee-981b-ad0bee74ec5f)



![image](https://github.com/user-attachments/assets/ee4c8a25-15b8-4bcc-8a6b-2a5c2524c412)



##  Confusion Matrix Summary:

The confusion matrix illustrates that classes like standing, walking, and
sitting were detected with high accuracy (e.g., 157 true positives for
standing), while some misclassifications occurred among running, armed,
and fighting, which often overlap in appearance and context.



![image](https://github.com/user-attachments/assets/c25025f0-cb63-4037-825c-53017cefd1a1)


##  Real-Time Performance

The detection system consistently ran at 30–40 frames per second (FPS)
on GPU, confirming real-time compatibility for surveillance applications.

##  Visual Output and Alerts

Bounding boxes with class labels were successfully rendered on video
frames. Detected abnormal actions triggered real-time audio alerts and
were logged with timestamps and labels. Annotated videos and saved
abnormal frames were generated for later review.

##  Heatmap and Movement Zones

The system produced motion heatmaps that visually highlighted areas of
frequent or abnormal activity, assisting in zone-based surveillance and
activity clustering.


![image](https://github.com/user-attachments/assets/ff8f6759-1f1f-43d5-a46e-05a5141e3b28)


The model successfully detected actions like running and sudden stopping, with
bounding boxes and labels for abnormal actions, offering reliable performance
for surveillance systems.


![image](https://github.com/user-attachments/assets/5967b4df-b0b5-47e4-a551-9885b56a8f26)


#  Future Scope for Improvement  #

## o Prospects for Enhancement :

The anomaly detection system created with YOLOv8 provides a solid basis
for real-time monitoring and can be improved with extra features and
cross-domain compatibility.

## o Sophisticated Crowd Behavior Examination :

Future enhancements may include clustering algorithms and density-
based methods to oversee mass movements, recognize crowd formations,
or pinpoint potentially aggressive group actions like riots or flash
mobs—crucial in public areas during occasions or demonstrations.

## o Improved Immediate Notifications and Spatial Consciousness:

Incorporating real-time heatmaps and dynamic crowd density analysis
would allow the system to automatically identify areas of concern. When
paired with localized alerts that include timestamps, this would facilitate
quick incident identification and reaction.

## o Smart Behavior Observation:

The system can be customized for specific environments such as retail
shops or industrial locations to identify activities like theft, misuse of tools
or machines, and other questionable or dangerous behaviors, thus
enhancing safety and minimizing operational risks.

## o Implementation in Various Areas:

In addition to surveillance, the approach might be applied to fields such as
intelligent transportation (e.g., spotting jaywalking or traffic incidents),
educational security (e.g., recognizing bullying or loitering), and wildlife
observation for tracking poaching or unusual animal activity in
conservation areas.

## o Automated Alerts and System Connectivity:

To enhance real-time responsiveness, the system might be connected with
mobile and web platforms to deliver instant alerts via SMS, email, or
messaging applications. This would guarantee that essential anomalies are
relayed promptly to security staff or system administrators.

These forthcoming improvements would enable the system to develop into
a robust and flexible solution, aiding not just in public safety but also in
workplace adherence, asset safeguarding, and environmental preservation


# Conclusion #

This venture presents an successful approach to anomalous movement
discovery by joining the capabilities of YOLOv8 with real-time movement
following and relevant investigation. The framework is planned to be both
effective and interpretable, requiring negligible explained information
whereas keeping up tall location exactness. By leveraging lightweight
profound learning models and commonsense computer vision methods, the
arrangement addresses real-world challenges in observation, particularly in
high-density or energetic environments.

Through the combination of question discovery and behavioral examination,
the framework gives solid, real-time recognizable proof of suspicious
exercises, such as sudden developments, gather clustering, or potential
dangers. This not as it were upgrades situational mindfulness but moreover
makes a difference diminish reliance on manual observing. Once completely
executed, the framework can altogether move forward reaction times and
decision-making in security-sensitive applications such as open security,
healthcare, and mechanical checking.
