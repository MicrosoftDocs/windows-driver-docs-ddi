---
UID: NS:ntdd8042._OUTPUT_PACKET
title: _OUTPUT_PACKET (ntdd8042.h)
description: OUTPUT_PACKET contains information about the data that is being written to a keyboard or mouse device by I8042prt.
old-location: hid\output_packet.htm
tech.root: hid
ms.assetid: 1d8d723f-aae5-499e-94cf-c7ccdb24c45f
ms.date: 04/30/2018
keywords: ["_OUTPUT_PACKET structure"]
ms.keywords: "*POUTPUT_PACKET, OUTPUT_PACKET, OUTPUT_PACKET structure [Human Input Devices], POUTPUT_PACKET, POUTPUT_PACKET structure pointer [Human Input Devices], _OUTPUT_PACKET, hid.output_packet, i8042ref_3e563892-06cb-4021-847d-d6afda279c7a.xml, ntdd8042/OUTPUT_PACKET, ntdd8042/POUTPUT_PACKET"
f1_keywords:
 - "ntdd8042/OUTPUT_PACKET"
 - "OUTPUT_PACKET"
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
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
- ntdd8042.h
api_name:
- OUTPUT_PACKET
product:
- Windows
targetos: Windows
req.typenames: OUTPUT_PACKET, *POUTPUT_PACKET
---

# _OUTPUT_PACKET structure


## -description


OUTPUT_PACKET contains information about the data that is being written to a keyboard or mouse device by I8042prt.


## -struct-fields




### -field Bytes

Pointer to an array of bytes being written to an i8042 port device.


### -field CurrentByte

Specifies the index of the next byte to write.


### -field ByteCount

Specifies the number of bytes in the array of bytes located at <b>Bytes</b>.


### -field State

Specifies one of the following write states:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef enum _TRANSMIT_STATE {
    Idle = 0,
    SendingBytes
} TRANSMIT_STATE;</pre>
</td>
</tr>
</table></span></div>




#### Idle

Identifies that a write is not in progress.



#### SendingBytes

Identifies that a write is in progress.


## -remarks



This structure is used with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd8042/nc-ntdd8042-pi8042_keyboard_isr">PI8042_KEYBOARD_ISR</a> callback routine and a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd8042/nc-ntdd8042-pi8042_mouse_isr">PI8042_MOUSE_ISR</a> callback routine.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff542294(v=vs.85)">KbFilter_IsrHook</a>



<a href="https://docs.microsoft.com/previous-versions/ff542379(v=vs.85)">MouFilter_IsrHook</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd8042/nc-ntdd8042-pi8042_keyboard_isr">PI8042_KEYBOARD_ISR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd8042/nc-ntdd8042-pi8042_mouse_isr">PI8042_MOUSE_ISR</a>
 

 

