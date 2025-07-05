#   Robust Human Target Detection
A fast expanding area of computer vision, human action detection has uses in
many different sectors including video surveillance, sports analysis, healthcare
monitoring, and human-computer interaction. These systems can increase
automation, boost safety, and create new user experiences by identifying and
classifying human activities including walking, running, or standing.


Human action detection&#39;s complexity results from elements including variations
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


#Scope of the project:

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


1. Efficient Real-Time Processing:
   
 Low Latency: The system will prioritize real-time performance, ensuring
that abnormal activities are detected and flagged with minimal delay. This
is critical for time-sensitive applications such as live surveillance or
emergency response.

 Hardware Optimization: By utilizing YOLOv8&#39;s lightweight architecture,
the system will be designed to run efficiently on standard hardware,
including edge devices like Raspberry Pi, GPUs, or CPUs, without
compromising on speed or accuracy.

 High Throughput: The system will process multiple input streams (e.g.,
from CCTV cameras or drones) simultaneously, providing scalability for
large-scale deployments.


![image](https://github.com/user-attachments/assets/ce6037be-94f4-4197-b0b3-8df14d4c6f83)


2. Context-Aware Anomaly Identification:

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


3. Data-Efficient Training and Generalization:

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


4. Explainable Output and Visual Feedback:

Transparency is key in surveillance systems. This project includes
interpretability tools that make the system&#39;s decisions clear and user-friendly.

 Bounding Boxes and Labels: Every detected individual is enclosed in a
box with activity labels (e.g., “walking”, “fighting”) and a confidence score.

 On-Screen Status Indicators: Abnormal behaviors are visually marked on
video feeds for real-time decision-making by operators.

 Heatmaps: A cumulative thermal map shows the zones with highest
activity or anomalies, helping in identifying hotspots or unusual
movements across time.

 Abnormal Frame Saving: Frames with detected anomalies are saved with
timestamps and activity types, creating a visual record for later reviews.


5. Automated Alerts and Intelligent Logging:

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


6. Scalable, Modular, and Cross-Domain Design

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


Input and Output:

Input:

The input to the abnormal activity detection system primarily consists of video
data obtained from live surveillance feeds or pre-recorded footage. These videos
may come from real-world environments such as public spaces, hospitals,
offices, or educational institutions. The goalhis to detect and classify human
actions within each frame in real time.

Video Collection:

 Videos were collected from simulated environments or sourced from
surveillance systems.

 Scenarios included publiciplaces, indoor rooms, streets, and hallways
under varied lighting and density conditions.

Custom Datasets:

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


Output:

The output of the system will consist of multiple actionable results for abnormal
activity detection:

 Visual Detection and Annotation :

The system provides real-time visual feedback by identifying individuals in the
video frames and markinguthem with bounding boxes. Each detected action is
labeled with a corresponding tag like &quot;Running&quot;, &quot;Fighting&quot;, or &quot;Robbery&quot;, and
each detection includes a confidence score indicating the system’s certainty. This
helps operators interpret situations instantly and with greater accuracy.

 Anomaly Logging and Metadata:

In addition to visual outputs, the system maintains a structured log file that
records details such as the timestamp, detected action, frame number, and the
duration of the event. The log may alsojinclude contextual information like
estimated crowd density or predefined thresholds for specific areas, aiding
deeper analysis and better scene understanding.


![image](https://github.com/user-attachments/assets/5a99cb1c-69ef-45be-a205-564274321f4c)



 Saved Annotated Frames:

Any frame in which an abnormal activity is detected is automatically saved in a
designated folder. Each file is timestamped and labeled with the type of anomaly,
making it easy to locate and review incidents later. The filenames follow a clear
format (e.g., fighting_12_05_2025_10_33_21.jpg) for traceability.

 Abnormality Heatmap:

A heatmap is created based on areas with high motion or recurring abnormal
activities. This visual tool helps identify hotspots or zones that require increased
attention, and it can also guide future decisions about camera placement or
crowd control measures.

 Real-Time Audio Alerts:

For high-risk actions like fights, armed threats, or robbery, the system triggers
distinct audio alerts. Each type of anomaly can have a unique tone, and a built-in
cooldown mechanism prevents the system from issuing repeated alerts for the
same event in quick succession.

 Performance Metrics:

In addition to the visual outputs, the system will log performance metrics such
as precision, recall, F1-score, and accuracy based on the model’s ability to
correctly detect abnormal actions, which can be helpful for evaluating and fine-
tuning the system.






