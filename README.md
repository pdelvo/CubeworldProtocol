Cube World Protocol
--------------------


##Data Types

Data Type  | Example     | Description
-----------|-------------|--------------
byte       | 10          | A 8 bit unsigned integer
int32      | 10          | A 32 bit signed integer (little endian)
int64      | 10          | A 64 bit signed integer (little endian)
uint32     | 10          | A 32 bit unsigned integer (little endian)
uint64     | 10          | A 64 bit unsigned integer (little endian)
string     | "Cubeworld" | A UTF 16 Little Endian Encoded string prefixed with its size in **chars**
byte array | { 1, 2, 3}  | A byte array, zlib compressed prefixed with its compressed size

##Packets

Each packet is prefixed with a unique packet id (int32).

Unknown (0x02)
-----------------
*Unknown*

Packet ID   | Field Name  | Field Type | Example   | Notes
------------|-------------|------------|-----------|----------------------------
0x02        | Empty?
Total Size: | 4 bytes

Unknown Client Version (0x03)
-----------------
*Server -> Client*

Is sent on wrong client version


Packet ID   | Field Name     | Field Type | Example   | Notes
------------|----------------|------------|-----------|----------------------------
0x03        | 
Total Size: | 4 bytes

Unknown (0x04)
-----------------
*Unknown*


Packet ID   | Field Name     | Field Type | Example    | Notes
------------|----------------|------------|------------|----------------------------
0x04        | ??
Total Size: | ?? bytes

Unknown (0x05)
-----------------
*Unknown*


Packet ID   | Field Name     | Field Type | Example    | Notes
------------|----------------|------------|------------|----------------------------
0x05        | Unknown        | int32?     | 0          | Unknown
            | Unknown        | uint32?    | 0xA0B46A04 | 0xA0B46A04 was spotted
Total Size: | 12 bytes

Unknown (0x10)
-----------------
*Unknown*

First Server -> Client packet


Packet ID   | Field Name  | Field Type | Example   | Notes
------------|-------------|------------|-----------|----------------------------
0x10        | Seems to be always 4464 bytes (+ id)
Total Size: | 4468 bytes

Unknown (0x11)
-----------------
*Unknown*

Is sent by the client on login


Packet ID   | Field Name     | Field Type | Example   | Notes
------------|----------------|------------|-----------|----------------------------
0x11        | Client Version | int32      | 3         | Current Client Version: 3
Total Size: | 8 bytes


World Seed (0x0F)
-----------------
*Unknown*

Packet ID   | Field Name  | Field Type | Example   | Notes
------------|-------------|------------|-----------|----------------------------
0x0F        | Seed        | int32      | 26879     | The Seed specified in server.cfg
Total Size: | 8 bytes
