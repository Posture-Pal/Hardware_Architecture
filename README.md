# Posture Pal Hardware Architecture

This repository contains the hardware architecture and related documentation for the **Posture Pal** project. It includes diagrams, schematics, and detailed descriptions of the physical hardware components and their interconnections. The repository serves as a guide for understanding the hardware design, functionality, and implementation process.

---

## Features
- 📐 **Physical Architecture Diagram**: Provides an overview of the hardware system layout.
- ⚙️ **Fritzing Diagram**: Visual representation of sensor connections and wiring.
- 📜 **Sensor Descriptions**: Detailed documents describing the functionalities of the various sensors used in the system.

---

## <img src="https://emojigraph.org/media/microsoft/gear_2699-fe0f.png" alt="alt text" width="20"> Hardware Components
### Sensors
- **BNO055 Orientation Sensor**: Tracks user posture and orientation.
- **DHT22 Sensor**: Measures temperature and humidity to monitor the environmental conditions.

### Actuators
- **Piezo Buzzer**: Provides sound alerts for poor posture.
- **Vibration Motor**: Offers haptic feedback to alert users about slouching.

### Central Processing Unit
- **Raspberry Pi 4 Model B**: Acts as the central processing unit for managing data collection, processing, and communication.

---

## Repository Contents
1. **Physical Architecture Diagram**
   - Overview of how the hardware components are physically arranged and connected.
     ![Screenshot 2024-12-13 195119](https://github.com/user-attachments/assets/62faceea-9060-491f-8741-98d7ec581a5d)
     
2. **Fritzing Diagram**
    - Detailed wiring schematic for replicating the hardware setup.
    ![Screenshot 2024-12-13 195100](https://github.com/user-attachments/assets/d858cac6-db49-47ad-aaa3-8cb96268c04b)
4. **Sensor Descriptions**
   - Document outlining the purpose and functionality of each sensor.

---

## How to Use
1. Clone the repository:
   ```bash
   git clone https://github.com/Posture-Pal/Hardware_Architecture.git
   cd Hardware_Architecture
   ```
2. Check the root folder for diagrams, including `PhysicalArchitecture.png` and `FinalFritzingDiagram_bb.png`.
3. Refer to the `system_hardware_description.md` for detailed insights into sensor functionalities.

---

## Acknowledgments
1. **Fritzing**: For providing tools to create detailed wiring diagrams.
2. **Adafruit**: For high-quality sensor libraries and resources.
3. **Raspberry Pi Foundation**: For the robust Raspberry Pi platform.

---

Feel free to open an issue for any questions or suggestions regarding the hardware architecture. Thank you for contributing to **Posture Pal**!
