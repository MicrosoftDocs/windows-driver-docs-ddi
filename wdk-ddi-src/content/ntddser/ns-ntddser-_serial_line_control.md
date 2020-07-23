---
UID: NS:ntddser._SERIAL_LINE_CONTROL
title: _SERIAL_LINE_CONTROL (ntddser.h)
description: The SERIAL_LINE_CONTROL structure describes the control settings for the serial line.
old-location: serports\serial_line_control.htm
tech.root: serports
ms.assetid: 2D11187E-B21B-4211-BAC0-248B93BAB6D5
ms.date: 04/23/2018
keywords: ["_SERIAL_LINE_CONTROL structure"]
ms.keywords: "*PSERIAL_LINE_CONTROL, PSERIAL_LINE_CONTROL, PSERIAL_LINE_CONTROL structure pointer [Serial Ports], SERIAL_LINE_CONTROL, SERIAL_LINE_CONTROL structure [Serial Ports], _SERIAL_LINE_CONTROL, ntddser/PSERIAL_LINE_CONTROL, ntddser/SERIAL_LINE_CONTROL, serports.serial_line_control"
f1_keywords:
 - "ntddser/SERIAL_LINE_CONTROL"
 - "SERIAL_LINE_CONTROL"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddser.h
api_name:
- SERIAL_LINE_CONTROL
targetos: Windows
req.typenames: SERIAL_LINE_CONTROL, *PSERIAL_LINE_CONTROL
---

# _SERIAL_LINE_CONTROL structure


## -description


The <b>SERIAL_LINE_CONTROL</b> structure describes the control settings for the serial line.


## -struct-fields




### -field StopBits

The number of stop bits used at the end of each character that is transmitted or received. This member is set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>STOP_BIT_1</td>
<td>One stop bit.</td>
</tr>
<tr>
<td>STOP_BITS_1_5</td>
<td>One and a half stop bits.</td>
</tr>
<tr>
<td>STOP_BITS_2</td>
<td>Two stop bits. Not valid if <b>WordLength</b> = 5.</td>
</tr>
</table>
 


### -field Parity

The type of parity checking used for each character that is transmitted or received. This member is set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>NO_PARITY</td>
<td>No parity bit is used.</td>
</tr>
<tr>
<td>ODD_PARITY</td>
<td>Odd parity is used. The parity bit is 0 if the number of 1s in the character value is odd. Otherwise, the parity bit is 1.</td>
</tr>
<tr>
<td>EVEN_PARITY</td>
<td>Even parity is used. The parity bit is 0 if the number of 1s in the character value is even. Otherwise, the parity bit is 1.</td>
</tr>
<tr>
<td>MARK_PARITY</td>
<td>The parity bit is always set to 1.</td>
</tr>
<tr>
<td>SPACE_PARITY</td>
<td>The parity bit is always set to 0.</td>
</tr>
</table>
 


### -field WordLength

Data bits per character. This member indicates the number of data bits in each character value that is transmitted or received, and does not include parity bits or stop bits. <b>WordLength</b> values in the range 5 to 8 are typically supported.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_line_control">IOCTL_SERIAL_GET_LINE_CONTROL</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_line_control">IOCTL_SERIAL_SET_LINE_CONTROL</a> requests.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_line_control">IOCTL_SERIAL_GET_LINE_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_line_control">IOCTL_SERIAL_SET_LINE_CONTROL</a>
 

 

