---
UID: NS:ntdd8042._OUTPUT_PACKET
title: "_OUTPUT_PACKET"
author: windows-driver-content
description: OUTPUT_PACKET contains information about the data that is being written to a keyboard or mouse device by I8042prt.
old-location: hid\output_packet.htm
old-project: hid
ms.assetid: 1d8d723f-aae5-499e-94cf-c7ccdb24c45f
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: hid.output_packet, ntdd8042/POUTPUT_PACKET, i8042ref_3e563892-06cb-4021-847d-d6afda279c7a.xml, OUTPUT_PACKET, POUTPUT_PACKET structure pointer [Human Input Devices], ntdd8042/OUTPUT_PACKET, OUTPUT_PACKET structure [Human Input Devices], POUTPUT_PACKET, _OUTPUT_PACKET, *POUTPUT_PACKET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntdd8042.h
apiname:
-	OUTPUT_PACKET
product: Windows
targetos: Windows
req.typenames: OUTPUT_PACKET, *POUTPUT_PACKET
---

# _OUTPUT_PACKET structure


## -description


OUTPUT_PACKET contains information about the data that is being written to a keyboard or mouse device by I8042prt.


## -syntax


````
typedef struct _OUTPUT_PACKET {
  PUCHAR         Bytes;
  ULONG          CurrentByte;
  ULONG          ByteCount;
  TRANSMIT_STATE State;
} OUTPUT_PACKET, *POUTPUT_PACKET;
````


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



This structure is used with a <a href="..\ntdd8042\nc-ntdd8042-pi8042_keyboard_isr.md">PI8042_KEYBOARD_ISR</a> callback routine and a <a href="..\ntdd8042\nc-ntdd8042-pi8042_mouse_isr.md">PI8042_MOUSE_ISR</a> callback routine.




## -see-also

<a href="https://msdn.microsoft.com/0feca7de-aa80-4d1e-a5fc-901c18169649">KbFilter_IsrHook</a>



<a href="..\ntdd8042\nc-ntdd8042-pi8042_mouse_isr.md">PI8042_MOUSE_ISR</a>



<a href="https://msdn.microsoft.com/34d0a7e9-4a1e-43ba-a643-800ebaadc360">MouFilter_IsrHook</a>



<a href="..\ntdd8042\nc-ntdd8042-pi8042_keyboard_isr.md">PI8042_KEYBOARD_ISR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20OUTPUT_PACKET structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

