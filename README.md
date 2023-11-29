# Smart_Parking_System
IoT-based Smart Parking System using NodeMCU ESP8266 presented in this project aims to address the challenges associated with urban parking by providing a seamless and automated solution. The system leverages the capabilities of NodeMCU, IR sensors, and two servo motors to create a smart parking infrastructure.
#Initilization
The setup function initializes the Smart Parking System by configuring various
components and establishing connections. It begins by attaching the servos to their
respective pins, setting up the entry and exit sensors as input pins, and configuring the
slots' input pins. The system also subscribes to Adafruit IO feeds for both entry and exit
gates, preparing to receive commands. Additionally, it initializes the NTP client for
accurate timekeeping and connects to the specified Wi-Fi network. The serial
communication is initiated for debugging purposes, providing essential information about
the system's status and interactions. Once connected to Wi-Fi, the system prints the IP
address to the serial monitor, indicating a successful initialization.
#Loop Function
The loop function of the Smart Parking System orchestrates the continuous operation of
the device. It first establishes and maintains a connection to the MQTT broker by calling
the MQTT_connect function. The system then updates the current time using the NTP
client, facilitating accurate timestamping of events. Subsequently, it reads the status of
entry and exit sensors, as well as the occupancy status of each parking slot. Based on
these inputs, the system increments or decrements the parking space count and controls
the servo motors to open and close the gates accordingly. The status of each parking slot
(occupied or available) is published to the corresponding Adafruit IO feeds. The loop
function also subscribes to the entry and exit gate feeds, responding to external
commands for gate control. A delay of 5000 milliseconds (5 seconds) is introduced to
control the loop's frequency.
#Calibration and Customization
The code is designed to facilitate easy calibration and customization for different parking
environments. Users can adjust the OPEN_ANGLE and CLOSE_ANGLE parameters to
fine-tune the gate servo positions. Additionally, the code allows for modification of Wi-Fi
credentials (SSID and password) and Adafruit IO authentication details (username and
AIO key) to suit specific network and platform configurations.
