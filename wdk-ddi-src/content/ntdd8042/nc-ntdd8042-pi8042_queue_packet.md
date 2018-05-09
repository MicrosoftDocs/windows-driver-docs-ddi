---
UID: NC:ntdd8042.PI8042_QUEUE_PACKET
title: PI8042_QUEUE_PACKET
author: windows-driver-content
description: The PI8042_QUEUE_PACKET-typed callback routine queues an input data packet for processing by the ISR DPC of a keyboard or mouse device. I8042prt provides this callback.
old-location: hid\pi8042_queue_packet.htm
old-project: hid
ms.assetid: f5d42701-b418-4bda-b936-3e0a1f57ac9d
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: PI8042_QUEUE_PACKET, PI8042_QUEUE_PACKET callback, QueuePacket, QueuePacket callback function [Human Input Devices], hid.pi8042_queue_packet, i8042ref_44eb4361-586b-4390-8aea-4e1470a70691.xml, ntdd8042/QueuePacket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
req.target-type: Desktop
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ntdd8042.h
api_name:
-	QueuePacket
product:
- Windows
targetos: Windows
req.typenames: 
---

# PI8042_QUEUE_PACKET callback function


## -description


The PI8042_QUEUE_PACKET-typed callback routine queues an input data packet for processing by the ISR DPC of a keyboard or mouse device. I8042prt provides this callback.


## -parameters




### -param Context [in]

Pointer to the function device object that represents a keyboard or mouse device.


## -returns



None




## -remarks



The PI8042_QUEUE_PACKET callback should only be called by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543248">PI8042_KEYBOARD_ISR</a> callback or a<a href="https://msdn.microsoft.com/library/windows/hardware/ff543252">PI8042_MOUSE_ISR</a> callback. I8042prt calls a vendor-supplied ISR callback in the corresponding I8042prt device ISR. 

I8042prt specifies the queue packet callback for a keyboard in the <b>QueueKeyboardPacket</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541039">INTERNAL_I8042_HOOK_KEYBOARD</a> structure that I8042prt uses with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541238">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a> request.

I8042prt specifies the queue packet callback for a mouse in the <b>QueueMousePacket</b> member of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541044">INTERNAL_I8042_HOOK_MOUSE</a> structure that I8042prt uses with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541242">IOCTL_INTERNAL_I8042_HOOK_MOUSE</a> request.

The PI8042_QUEUE_PACKET callback runs in kernel mode at the same IRQL as the I8042prt ISR for the device.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541039">INTERNAL_I8042_HOOK_KEYBOARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541044">INTERNAL_I8042_HOOK_MOUSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541238">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541242">IOCTL_INTERNAL_I8042_HOOK_MOUSE</a>
 

 

