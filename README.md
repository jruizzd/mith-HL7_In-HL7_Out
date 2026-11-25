## Mirth HL7 Gateway

# Project Overview

This project demonstrates a basic HL7 file-processing workflow using Mirth Connect.

The project uses a parent directory called mirth-hl7-gateway containing two subdirectories:

# mirth-hl7-gateway/

│
├── HL7_In/
│ └── \*.hl7
│
└── HL7_Out/
└── output.hl7
HL7 messages are manually created in Notepad and saved in the HL7_In folder. Mirth Connect reads the incoming HL7 files and writes the processed message to the HL7_Out folder.

# Components

Source Connector
Connector Type: File Reader

Directory:

HL7_In
File Filter Pattern:

\*.hl7
The source connector monitors the folder for HL7 files and processes any file matching the .hl7 extension.

Destination Connector
Connector Type: File Writer

Directory:

HL7_Out
Output File Name:

output.hl7
The destination connector writes the processed message to the output folder.

Sample HL7 Message
MSH|^~\&|EMR|HOSPITAL|RIS|RAD|202611241000||ORM^O01|1001|P|2.3
PID|1||1001^^^HOSPITAL||DOE^JOHN||19900101|M
PV1|1|O
ORC|NW|ORD12345
OBR|1|ORD12345||CHEST2V^Chest X-Ray 2 Views
Testing Procedure
Create an HL7 message using Notepad.
Save the file in the HL7_In folder with a .hl7 extension.
Deploy and start the channel in Mirth Connect.
Mirth reads the HL7 file using the File Reader source connector.
The message is processed and written to HL7_Out/output.hl7.
Verify the output file was created successfully.
Important Note
Previously processed HL7 files should not be reused.

For each test:

Create a new HL7 file.
Use a different Message Control ID (MSH-10).
Use a different Order Number (ORC-2 / OBR-2).
Example
MSH|^~\&|EMR|HOSPITAL|RIS|RAD|202611241005||ORM^O01|1002|P|2.3
PID|1||1002^^^HOSPITAL||SMITH^JANE||19850515|F
PV1|1|O
ORC|NW|ORD12346
OBR|1|ORD12346||HANDLT^Left Hand X-Ray
This ensures Mirth processes the message as a new order.

# Technologies Used

Mirth Connect
HL7 v2.x
File Reader Connector
File Writer Connector
Notepad
Git
GitHub
