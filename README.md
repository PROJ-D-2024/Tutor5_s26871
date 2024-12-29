# Forest Surveillance and Recognition System

This project involves the development of a surveillance system designed to recognize people in forested areas. The system utilizes advanced machine learning algorithms and computer vision techniques to detect suspicious activity and identify individuals, while enabling data analysis and real-time decision-making.

## System Architecture

The system comprises several interconnected components that work together to ensure robust recognition and analysis:

### Components

#### 1. **DroneController**
   - **Purpose**: Controls the movement of the drone.
   - **Key Functions**:
     - `MoveForward()`: Moves the drone forward.
     - `MoveLeft()`: Moves the drone to the left.
     - `MoveRight()`: Moves the drone to the right.
     - `MoveBack()`: Moves the drone backward.
     - `CalculateDepth()`: Calculates the depth to avoid obstacles.

#### 2. **Recognition**
   - **Purpose**: Handles the detection and recognition of people or suspicious activities.
   - **Key Functions**:
     - `UseYolo()`: Activates YOLO (You Only Look Once) algorithm for object detection.
     - `StopYolo()`: Stops the YOLO detection process.
     - `RaiseSuspicious()`: Flags areas or objects as suspicious.

#### 3. **Pre Render Class**
   - **Purpose**: Pre-processes elements for rendering and ensures data quality.
   - **Key Attributes**:
     - `Element` (String): Element to process.
   - **Key Functions**:
     - `CheckQuality()`: Ensures data meets quality standards.

#### 4. **Training Class**
   - **Purpose**: Trains and fine-tunes models for better recognition accuracy.
   - **Key Attributes**:
     - `DBAccess`: Object for database access.
     - `Photos`: List of photos for training.
   - **Key Functions**:
     - `Train()`: Trains the recognition model.
     - `Correlate()`: Correlates current data with past data.
     - `ShowDifference()`: Highlights differences in data for analysis.
     - `IntegrateBest()`: Integrates the best models and data.

#### 5. **Control Class**
   - **Purpose**: Manages the system's operation and displays flagged areas.
   - **Key Attributes**:
     - `SuspiciousZones`: List of flagged objects or areas.
     - `Size`: String indicating size of areas.
   - **Key Functions**:
     - `StartProgram()`: Starts the surveillance program.
     - `ShowSuspiciousZone()`: Displays areas flagged as suspicious.

### Data Flow
1. **Drone Movement**: The `DroneController` directs the drone to patrol the forest.
2. **Recognition**: The `Recognition` class processes the data captured by the drone’s cameras, applying YOLO to detect individuals or suspicious activity.
3. **Training**: The `Training Class` refines recognition models with data from the field.
4. **Control and Alert**: The `Control Class` highlights and manages suspicious zones.
5. **Quality Check**: The `Pre Render Class` ensures data integrity before rendering results.

### Technology Stack
- **MongoDB**: Database for storing captured images and training data.
- **YOLO Algorithm**: Real-time object detection.
- **OpenCV**: Library for image and video processing.
- **Python**: Programming language for system implementation.

