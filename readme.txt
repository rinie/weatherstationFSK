weatherstationFSK uses an adapted version of the RF12mod driver.
It is adapted such that fixed length packages can be received.
A external function rf12_setFixedLength(uint8_t packet_len) is provided.
With packet_len > 0 exactly this maximum number of bytes is received, and
no checks on  rf12_len (= rf12_buf[2]) will be done.
With packet_len = 0, the driver fucntions as before and is intended to
receive standard RF12-driver packages.

To install:
1. create a folder RF12WS in the arduino libraries folder:
      arduino/libraries/RF12WS
2. copy RF12WS.h and RF12WS.cpp to this folder
3. create a folder weatherstationFSK in the arduino base folder
      arduino/weatherstationFSK
4. copy weatherstationFSK.ino to this folder
5. when already active, close the arduino IDE
      added libraries and projects are only seen at startup
6. start the arduino IDO, and select the sketch weatherstationFSK

Use:
The amount of information printed can be controlled by setting some #defines 
in the first view lines of the weatherstationFASK.ino:
    //Define the printed output
    //#define LOGRAW 1 //comment = disable, uncomment = enable logging received package group_id 212 (0xD4)
    //#define LOGPKT 1 //comment = disable, uncomment = enable logging unique package passing crc
    #define LOGDCF 1 //comment = disable, uncomment = enable updating time and logging of DCF77 values
    #define LOGDAT 1 //comment = disable, uncomment = enable logging of parsed sensor data


