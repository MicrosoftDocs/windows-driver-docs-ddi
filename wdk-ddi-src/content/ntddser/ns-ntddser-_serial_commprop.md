---
UID: NS:ntddser._SERIAL_COMMPROP
title: "_SERIAL_COMMPROP"
author: windows-driver-content
description: The SERIAL_COMMPROP structure specifies the properties of a serial port.
old-location: serports\serial_commprop.htm
tech.root: serports
ms.assetid: 1C8610F5-A397-4CDE-890D-7AA5AD94A6AF
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PSERIAL_COMMPROP, PSERIAL_COMMPROP, PSERIAL_COMMPROP structure pointer [Serial Ports], SERIAL_COMMPROP, SERIAL_COMMPROP structure [Serial Ports], _SERIAL_COMMPROP, ntddser/PSERIAL_COMMPROP, ntddser/SERIAL_COMMPROP, serports.serial_commprop"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddser.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddser.h
api_name:
-	SERIAL_COMMPROP
product:
- Windows
targetos: Windows
req.typenames: SERIAL_COMMPROP, *PSERIAL_COMMPROP
---

# _SERIAL_COMMPROP structure


## -description


The <b>SERIAL_COMMPROP</b> structure specifies the properties of a serial port.


## -struct-fields




### -field PacketLength

The size, in bytes, of the data packet that starts with this structure and that contains the requested property data. This size includes the <b>SERIAL_COMMPROP</b> structure and any additional <b>ProvChar</b> array elements that follow this structure.


### -field PacketVersion

The version of this structure. The current version number is 2.


### -field ServiceMask

A bitmask that indicates which services are implemented by this communications provider. This member is always set to SERIAL_SP_SERIALCOMM by serial communications providers, including modem providers. The <b>ProvSubType</b> member indicates the specific type of serial communications that are implemented (for example, modem).


### -field Reserved1

Not used.


### -field MaxTxQueue

Maximum transmit queue size. The maximum size, in bytes, of the serial controller driver's internal output buffer. A value of zero indicates that no maximum value is imposed by the serial provider.


### -field MaxRxQueue

Maximum receive queue size. The maximum size, in bytes, of the serial controller driver's internal input buffer. A value of zero indicates that no maximum value is imposed by the serial provider.


### -field MaxBaud

The maximum acceptable baud rate. An <a href="https://msdn.microsoft.com/4A9B80F1-4DE1-4D35-ADDF-90058A4F8388">extension-based serial controller driver</a> sets this member to a baud rate expressed in bits per second (bps). For example, if the serial controller supports a maximum baud rate of 115,200 bps, the driver sets <b>MaxBaud</b> = 115200.

However, Serial.sys and many older serial controller drivers set <b>MaxBaud</b> to one of the SERIAL_BAUD_<i>XXX</i> flag bits that are defined in the Ntddser.h header file. The following values are defined for this member.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>SERIAL_BAUD_075</td>
<td>75 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_110</td>
<td>110 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_134_5</td>
<td>134.5 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_150</td>
<td>150 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_300</td>
<td>300 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_600</td>
<td>600 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_1200</td>
<td>1,200 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_1800</td>
<td>1,800 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_2400</td>
<td>2,400 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_4800</td>
<td>4,800 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_7200</td>
<td>7,200 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_9600</td>
<td>9,600 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_14400</td>
<td>14,400 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_19200</td>
<td>19,200 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_38400</td>
<td>38,400 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_56K</td>
<td>56,000 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_57600</td>
<td>57,600 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_115200</td>
<td>115,200 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_128K</td>
<td>128,000 bps</td>
</tr>
<tr>
<td>SERIAL_BAUD_USER</td>
<td>Programmable baud rates are available.</td>
</tr>
</table>
 


### -field ProvSubType

The specific communications provider type. When the <b>ServiceMask</b> member is set to SERIAL_SP_SERIALCOMM, <b>ProvSubType</b> is set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>SERIAL_SP_UNSPECIFIED</td>
<td>Unspecified</td>
</tr>
<tr>
<td>SERIAL_SP_RS232</td>
<td>RS-232 serial port</td>
</tr>
<tr>
<td>SERIAL_SP_PARALLEL</td>
<td>Parallel port</td>
</tr>
<tr>
<td>SERIAL_SP_RS422</td>
<td>RS-422 serial port</td>
</tr>
<tr>
<td>SERIAL_SP_RS423</td>
<td>RS-423 serial port</td>
</tr>
<tr>
<td>SERIAL_SP_RS449</td>
<td>RS-449 serial port</td>
</tr>
<tr>
<td>SERIAL_SP_MODEM</td>
<td>Modem device</td>
</tr>
<tr>
<td>SERIAL_SP_FAX</td>
<td>FAX device</td>
</tr>
<tr>
<td>SERIAL_SP_SCANNER</td>
<td>Scanner device</td>
</tr>
<tr>
<td>SERIAL_SP_BRIDGE</td>
<td>Unspecified network bridge</td>
</tr>
<tr>
<td>SERIAL_SP_LAT</td>
<td>LAT protocol</td>
</tr>
<tr>
<td>SERIAL_SP_TELNET</td>
<td>TCP/IP Telnet® protocol</td>
</tr>
<tr>
<td>SERIAL_SP_X25</td>
<td>X.25 standards</td>
</tr>
</table>
 


### -field ProvCapabilities

The capabilities offered by the provider. This member is set to zero or to the bitwise-OR of one or more of the following flag bits.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>SERIAL_PCF_DTRDSR</td>
<td>DTR (data terminal ready) and DSR (data set ready) are supported.</td>
</tr>
<tr>
<td>SERIAL_PCF_RTSCTS</td>
<td>RTS (request to send) and CTS (clear to send) are supported.</td>
</tr>
<tr>
<td>SERIAL_PCF_CD</td>
<td>CD (carrier detect) is supported.</td>
</tr>
<tr>
<td>SERIAL_PCF_PARITY_CHECK</td>
<td>Parity checking is supported.</td>
</tr>
<tr>
<td>SERIAL_PCF_XONXOFF</td>
<td>XON (transmit on) and XOFF (transmit off) flow control are supported.</td>
</tr>
<tr>
<td>SERIAL_PCF_SETXCHAR</td>
<td>The XON and XOFF characters are settable.</td>
</tr>
<tr>
<td>SERIAL_PCF_TOTALTIMEOUTS</td>
<td>Total-elapsed-time time-outs are supported.</td>
</tr>
<tr>
<td>SERIAL_PCF_INTTIMEOUTS</td>
<td>Interval time-outs are supported.</td>
</tr>
<tr>
<td>SERIAL_PCF_SPECIALCHARS</td>
<td>Special characters are supported.</td>
</tr>
<tr>
<td>SERIAL_PCF_16BITMODE</td>
<td>Special 16-bit mode is supported.</td>
</tr>
</table>
 


### -field SettableParams

A bitmask that indicates the communication parameter that can be changed. This member is set to zero or to the bitwise-OR of one or more of the following flag bits.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>SERIAL_SP_PARITY</td>
<td>Parity type (even or odd)</td>
</tr>
<tr>
<td>SERIAL_SP_BAUD</td>
<td>Baud rate</td>
</tr>
<tr>
<td>SERIAL_SP_DATABITS</td>
<td>Data bits</td>
</tr>
<tr>
<td>SERIAL_SP_STOPBITS</td>
<td>Stop bits</td>
</tr>
<tr>
<td>SERIAL_SP_HANDSHAKING</td>
<td>Handshaking (flow control)</td>
</tr>
<tr>
<td>SERIAL_SP_PARITY_CHECK</td>
<td>Parity checking</td>
</tr>
<tr>
<td>SERIAL_SP_CARRIER_DETECT</td>
<td>Carrier detect</td>
</tr>
</table>
 


### -field SettableBaud

A bitmask that indicates the baud rates that can be used. For a table that describes the SERIAL_BAUD_<i>XXX</i> flag bits that are defined for this member, see the description of the <b>MaxBaud</b> member. <b>SettableBaud</b> is set to zero or to the bitwise-OR or one or more of these flag bits.

Serial controller drivers set the SERIAL_BAUD_USER flag bit in the <b>SettableBaud</b> bitmask value to indicate that they support higher baud rates than those that can be expressed by the other SERIAL_BAUD_<i>XXX</i> flag bits. For example, a driver that supports baud rates of 57600, 115200, 230400, and 460800 bps sets <b>SettableBaud</b> = (SERIAL_BAUD_57600 |  SERIAL_BAUD_115200 |  SERIAL_BAUD_USER).


### -field SettableData

The number of data bits that can be set. This member is set to zero or to the bitwise-OR of one or more of the following flag bits.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>SERIAL_DATABITS_5</td>
<td>5 data bits</td>
</tr>
<tr>
<td>SERIAL_DATABITS_6</td>
<td>6 data bits</td>
</tr>
<tr>
<td>SERIAL_DATABITS_7</td>
<td>7 data bits</td>
</tr>
<tr>
<td>SERIAL_DATABITS_8</td>
<td>8 data bits</td>
</tr>
<tr>
<td>SERIAL_DATABITS_16</td>
<td>16 data bits</td>
</tr>
<tr>
<td>SERIAL_DATABITS_16X</td>
<td>Special wide path through serial hardware lines</td>
</tr>
</table>
 


### -field SettableStopParity

The stop-bit and parity settings that can be selected. This member is set to zero or to the bitwise-OR of one or more of the following flag bits.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>SERIAL_STOPBITS_10</td>
<td>One stop bit.</td>
</tr>
<tr>
<td>SERIAL_STOPBITS_15</td>
<td>One and a half stop bits.</td>
</tr>
<tr>
<td>SERIAL_STOPBITS_20</td>
<td>Two stop bits.</td>
</tr>
<tr>
<td>SERIAL_PARITY_NONE</td>
<td>No parity bit is used.</td>
</tr>
<tr>
<td>SERIAL_PARITY_ODD</td>
<td>Odd parity. The parity bit is 1 if the number of 1s in the character value is even. Otherwise, the parity bit is 0.</td>
</tr>
<tr>
<td>SERIAL_PARITY_EVEN</td>
<td>Even parity. The parity bit is 1 if the number of 1s in the character value is odd. Otherwise, the parity bit is 0.</td>
</tr>
<tr>
<td>SERIAL_PARITY_MARK</td>
<td>The parity bit is always set to 1.</td>
</tr>
<tr>
<td>SERIAL_PARITY_SPACE</td>
<td>The parity bit is always set to 0.</td>
</tr>
</table>
 


### -field CurrentTxQueue

Transmit queue size. This member specifies the size, in bytes, of the serial controller driver's internal output buffer. A value of zero indicates that the buffer size is unavailable.

For SerCx2 and SerCx, the associated serial controller driver typically sets this member to zero. Serial.sys sets this member to a nonzero value that indicates the output buffer size.


### -field CurrentRxQueue

Receive queue size. This member specifies the size, in bytes, of the serial controller driver's internal input buffer. A value of zero indicates that the buffer size is unavailable.

For SerCx2 and SerCx, this member is set by the associated serial controller driver. For SerCx2, the driver typically sets this member to zero. For SerCx, the driver typically sets this member to the size of the ring buffer that SerCx uses to buffer received data. This driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406704">SerCxGetRingBufferUtilization</a> method to get the ring buffer size from SerCx.

Serial.sys sets this member to a nonzero value that indicates the input buffer size.


### -field ProvSpec1

Provider-specific data. Applications should ignore this member unless provider-specific data about the data format required by the serial port is available.


### -field ProvSpec2

Provider-specific data. Applications should ignore this member unless provider-specific data about the data format required by the serial port is available.


### -field ProvChar

Provider-specific data. Applications should ignore this member unless provider-specific data about the data format required by the serial port is available. This member is the first element in a wide-character array of one or more elements. Any additional elements immediately follow this member. The <b>PacketLength</b> member specifies the size of the <b>SERIAL_COMMPROP</b> structure plus any additional <b>ProvChar</b> array elements that follow this structure.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546597">IOCTL_SERIAL_GET_PROPERTIES</a> request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546597">IOCTL_SERIAL_GET_PROPERTIES</a>
 

 

