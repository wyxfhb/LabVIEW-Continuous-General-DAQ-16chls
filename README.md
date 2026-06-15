
# LabVIEW General DAQ Program - 16 Channels

## Overview
This project provides a LabVIEW-based continuous data acquisition (DAQ) system supporting up to **16 channels**. It is designed for flexible use in both development and deployment scenarios, allowing users to run the system directly in LabVIEW or as a standalone desktop application.

---

## Features
- Continuous data acquisition for up to 16 channels  
- Modular LabVIEW architecture  
- Scalable and adaptable for different DAQ setups  
- Option to run in development mode or as a built executable  

---

## Requirements

### Development Environment
- LabVIEW (version 2021+)
- NI-DAQmx

### Runtime (Executable)
- LabVIEW Runtime Engine (matching the LabVIEW version used to build)
- NI-DAQmx Runtime

---

## How to Run the Application

There are **two ways to use this program**:

---

### Option 1 — Run in LabVIEW Development Environment

1. Clone the repository  
2. Open the `.lvproj` file

<img alt="File explorer view image" src="https://github.com/user-attachments/assets/5ef67876-4808-4820-b270-9afaa12079e9" />

> **Important:** The program must be run from the LabVIEW Project to function correctly. 

4. In the Project Explorer, locate and open `Main.vi`

<img alt="Project explorer image" src="https://github.com/user-attachments/assets/727fe948-37db-4901-8aca-72b38ce84ed7" />


6. Press the **Run** arrow to start the application

<img alt="LabVIEW run arrow image" src="https://github.com/user-attachments/assets/f7a047d4-6e50-4355-b719-c35e94e7a697" />

This approach is ideal for:
- Development and modification  
- Debugging  
- Learning how the system works  

---

### Option 2 — Build and Run as a Desktop Application

You can also build the application into a standalone executable.

#### To build the executable:

1. Open the LabVIEW project (`.lvproj`)
<img alt="File explorer view image" src="https://github.com/user-attachments/assets/5ef67876-4808-4820-b270-9afaa12079e9" />

> **Important:** The program must be run from the LabVIEW Project to function correctly. 

3. In the Project Explorer, expand:  
   **Build Specifications**  

4. Locate the build specification named:  
   **`GCD EXE`**  

5. Right-click **GCD EXE**  

6. Select **Build**

<img alt="Build GCD EXE image" src="https://github.com/user-attachments/assets/5fb56bef-6313-4470-8f73-47826fc6da39" />


---

### Build Output Location

The executable will be generated at:

C:\General Continuous DAQ App

---

### Running the Built Application

Once built:
- Navigate to the output directory  
- Launch the `.exe` file directly

<img alt="EXE in file explorer image" src="https://github.com/user-attachments/assets/a1efc2e4-3558-4846-86ce-b5801dc9b610" />

No LabVIEW development environment is required to run the application (only the appropriate runtime dependencies).

---
## How to use the program once running
After you have got the program running via either option 1 or 2 as shown above, follow the below instructions to effectively use the program:

### Configure File Setup

When prompted, enter a **file name** for saving your recorded data.  
- If left blank, a default name will be used:  
  **Experiment Result – [date and time]**

All saved result files are stored in the **Result Files** folder.

<img alt="Results files image" src="https://github.com/user-attachments/assets/96e2accf-b3f8-4c54-859f-8ac59ec3d410" />

---

### Configure Device and Settings
- Select your **Device Name**  
- Enter the **Sample Rate**  
- If you want recording to stop automatically after a fixed duration, enter a value in **Record Time (s)** and enable **Use Record Time**

<img alt="Device settings image" src="https://github.com/user-attachments/assets/699a277b-19d4-4c26-9c64-411aea971b7a" />

Click **INITIALISE VOLTAGE CHANNELS**.  
A configuration window will appear.

#### Channel Configuration
For each channel:
- Enter **Description**
- Enter **Scale**
- Enter **Offset**
- Tick **Select Ch** to enable the channel

Click **UPDATE** when finished.

<img alt="Channel dialog image" src="https://github.com/user-attachments/assets/6e4e2d5e-5906-462a-9605-83e84c075ef5" />

---

### Start Data Acquisition
Click **Start** to begin acquiring data.

#### Recording Data
You may start or stop recording data at any time during a run using the **Record** checkbox.

##### Recording behaviour
- When **Record** is **unchecked**, the program continues acquiring and displaying data, but data is **not** written to file.
- When **Record** is **checked**, the program begins recording data to file.

Two recording modes are available depending on whether **Use Record Time** is enabled:

---

#### A. Continuous Recording
If **Use Record Time** is **unchecked**, checking **Record** starts recording and recording continues until:
- **Record** is unchecked manually, or
- the program is stopped

<img alt="Record time unticked image" src="https://github.com/user-attachments/assets/a2205d90-976e-4360-af96-bf4a38e5dbb1" />

---

#### B. Timed Recording
If **Use Record Time** is **checked**, checking **Record** starts recording immediately and the program records for the duration entered in **Record Time (s)**.

For example:
- if **Record Time (s)** is set to **10**
- and **Use Record Time** is enabled
- checking **Record** will record for **10 seconds from that moment**

At the end of the timed interval:
- recording stops automatically
- the **Record** checkbox is reset automatically

The timed recording feature can be used **multiple times during the same run**.  
For example, if **Record Time (s)** remains set to **10**, you can check **Record** later in the run to record for **another 10 seconds**.

<img alt="Record time ticked image" src="https://github.com/user-attachments/assets/2b46a6f0-306d-4b70-a6ac-5083877b69ba" />

---

### Stopping the Program
- Press **Stop** to stop data acquisition
- You can repeat recording during a run as required
- When you are completely finished, close the window  
  **Always press Stop first** before closing to ensure your data file is saved correctly

<img alt="Stopping image" src="https://github.com/user-attachments/assets/d1a50d95-8619-4fc2-8871-8e880ba99366" />

---

## Notes
- The program must be run from the **LabVIEW Project** (`*.lvproj`)
- Result files are saved in the **Result Files** folder
- **Use Record Time** is optional
- When **Use Record Time** is enabled, the value in **Record Time (s)** is treated as the recording duration from the moment **Record** is checked
- Timed recording can be repeated multiple times during a single acquisition run

---

If you need help or wish to modify the program for your application, please contact the **Electronics & Software Labs**.
