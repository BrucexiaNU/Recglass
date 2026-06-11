# Health Sensing Evaluation

This directory contains supplementary materials for the health-sensing evaluation described in the paper.

## Overview

The health-sensing evaluation investigates whether a modular glasses-based wearable platform can support multiple physiological and behavioral sensing tasks using different sensor configurations.

Four sensing tasks were evaluated:

* Breathing monitoring
* Heart-rate monitoring
* Eye-movement detection
* Emotion-related sensing

The evaluation used different combinations of physiological and behavioral sensing modules, including:

* Bone-conduction microphone (BCM)
* Photoplethysmography (PPG)
* Electrooculography (EOG)
* Multimodal physiological sensing

A total of 14 participants were involved in the overall evaluation.

---

## Data Collection Settings

### Breathing Monitoring

* Sensor: BCM
* Sampling Rate: 16 kHz
* Participants: 14
* Placement: both sides of the nose bridge
* Data Collection Protocol:
  - Participants wore BCM modules positioned on both sides of the nose bridge.
  - Participants were instructed to perform normal breathing as well as intentionally vary their breathing rate.
  - Breathing conditions included normal breathing, slower breathing, and faster breathing.
  - BCM signals were continuously recorded throughout the experiment.
  - After each condition, participants provided self-reported feedback regarding their breathing condition.
* Task labels: self-reported breathing conditions
* Conditions: normal, slow, and fast breathing

### Heart-Rate Monitoring

* Sensor: PPG
* Sampling Rate: 100 Hz
* Participants: 14
* Placement: adjustable glasses-arm rail near the temple region
* Reference: commercial wrist-based heart-rate monitor
* Data Collection Protocol:
  - Participants simultaneously wore the glasses and a commercial wrist-based heart-rate monitor.
  - Participants first completed a resting session while seated.
  - Participants then completed an activity session involving normal walking within the laboratory environment.
  - PPG signals and reference heart-rate measurements were continuously recorded throughout both sessions.
  - Heart-rate estimates derived from the temple-mounted PPG signals were compared against the measurements reported by the reference device.
* Metric: Heart-rate estimation error relative to the reference device

### Eye-Movement Detection

* Sensor: EOG
* Sampling Rate: 250 Hz
* Participants: 14
* Placement:
  - Two EOG sensing modules were on the adjustable rails integrated into the glasses-arms. Each sensing module provided electrode connections that could be repositioned according to the desired sensing configuration.
  - Horizontal EOG electrodes were positioned around the outer corners of the eyes to capture left-right eye movements.
  - Vertical EOG electrodes were positioned above and below one eye to capture up-down eye movements and blinks.
  - Reference electrodes were placed on the mastoid region behind the ears.
* Classes: left gaze, right gaze, up gaze, down gaze, blink
* Data Collection Protocol:
  - Each participant completed a 4-minute guided recording session.
  - During the session, participants were instructed to repeatedly perform the five predefined eye gestures following verbal prompts from the experimenter.
  - Each gesture began from a neutral forward-looking position and returned to the neutral position before the next gesture.
* Sample Generation:
  - The recorded EOG signals were segmented into 2-second samples for classification.
  - Each sample was assigned the label of the corresponding instructed eye gesture.
* Reference labels: instructed gesture labels
* Metric: five-class classification accuracy

### Emotion-Related Sensing

* Sensors: PPG, BCM, and EOG
* Participants: 14
* Stimuli: emotion-eliciting video clips
* Data Collection Protocol:
  - Each participant viewed eight emotion-eliciting video clips.
  - Each video clip had a duration of approximately 2 minute.
  - After viewing each clip, participants provided self-reported valence and arousal ratings.
  - The reported ratings were used as affective labels for the corresponding recording session.
* Labels: participant self-reported valence and arousal
* Label mapping: 
  - Positive valence / high arousal
  - Positive valence / low arousal
  - Negative valence / high arousal
  - Negative valence / low arousal
* Sample Generation:
  - Physiological signals were segmented using 10-second windows.
  - Consecutive windows were generated with 50% overlap.
  - Each generated window inherited the valence and arousal label associated with the corresponding video clip.
* Metrics: four-class emotion classification, binary valence classification, and binary arousal classification

---

## Summary of Results

### Breathing Monitoring
Breathing patterns captured by BCM signals showed strong agreement with participant-reported breathing conditions.

### Heart-Rate Monitoring

- Average heart-rate estimation error: < 5%

### Eye-Movement Detection

- Five-class classification accuracy: 91%

### Emotion-Related Sensing

- Four-class emotion classification: 47.5%
- Binary valence classification: 65.0%
- Binary arousal classification: 71.2%

This task was used as an exploratory evaluation of emotion-related physiological sensing rather than as the primary target application.

