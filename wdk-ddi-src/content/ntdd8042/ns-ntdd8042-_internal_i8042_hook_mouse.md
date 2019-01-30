---
UID: NS:ntdd8042._INTERNAL_I8042_HOOK_MOUSE
title: _INTERNAL_I8042_HOOK_MOUSE (ntdd8042.h)
description: INTERNAL_I8042_HOOK_MOUSE is used by I8042prt to connect an optional callback routine that supplements the operation of the mouse ISR. The callback can be supplied by an optional, vendor-supplied, upper-level filter driver.
old-location: hid\internal_i8042_hook_mouse.htm
tech.root: hid
ms.assetid: 7ac9fc14-9e94-412b-811a-6013d46020a0
ms.date: 04/30/2018
ms.keywords: "*PINTERNAL_I8042_HOOK_MOUSE, INTERNAL_I8042_HOOK_MOUSE, INTERNAL_I8042_HOOK_MOUSE structure [Human Input Devices], PINTERNAL_I8042_HOOK_MOUSE, PINTERNAL_I8042_HOOK_MOUSE structure pointer [Human Input Devices], _INTERNAL_I8042_HOOK_MOUSE, hid.internal_i8042_hook_mouse, i8042ref_23133caf-3bd0-4160-8213-899e37b7703e.xml, ntdd8042/INTERNAL_I8042_HOOK_MOUSE, ntdd8042/PINTERNAL_I8042_HOOK_MOUSE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntdd8042.h
api_name:
-	INTERNAL_I8042_HOOK_MOUSE
product:
- Windows
targetos: Windows
req.typenames: INTERNAL_I8042_HOOK_MOUSE, *PINTERNAL_I8042_HOOK_MOUSE
---

# _INTERNAL_I8042_HOOK_MOUSE structure


## -description


INTERNAL_I8042_HOOK_MOUSE is used by I8042prt to connect an optional callback routine that supplements the operation of the mouse ISR. The callback can be supplied by an optional, vendor-supplied, upper-level filter driver.


## -struct-fields




### -field Context

Pointer, if non-<b>NULL</b>, to the context that must be used with the <b>IsrRoutine</b> routine. Otherwise, <b>Context</b> is <b>NULL</b>. 


### -field IsrRoutine

Pointer, if non-<b>NULL</b>, to an optional <a href="https://msdn.microsoft.com/library/windows/hardware/ff543252">PI8042_MOUSE_ISR</a> callback that customizes the operation of the I8042prt mouse ISR. Otherwise, <b>IsrRoutine </b>is <b>NULL</b>. 


### -field IsrWritePort

Pointer to the system-supplied mouse <a href="https://msdn.microsoft.com/library/windows/hardware/ff543231">PI8042_ISR_WRITE_PORT</a> callback, which writes data to a mouse.


### -field QueueMousePacket

Pointer to the system-supplied mouse <a href="https://msdn.microsoft.com/library/windows/hardware/ff543263">PI8042_QUEUE_PACKET</a> callback, which queues a mouse input data packet for processing by the mouse's ISR deferred procedure call. 


### -field CallContext

Pointer to the context that must be used with the <b>IsrWritePort</b> and <b>QueueMousePacket</b> routines. 


## -remarks



This structure is only used with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541242">IOCTL_INTERNAL_I8042_HOOK_MOUSE</a> request. 

<b>Context</b>, <b>InitializationRoutine</b>, and <b>IsrRoutine</b> can be supplied by an optional, vendor-supplied, upper-level filter driver. 

<b>IsrWritePort</b>, <b>QueueMousePacket</b>, and <b>CallContext</b> are supplied by I8042prt.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541242">IOCTL_INTERNAL_I8042_HOOK_MOUSE</a>



<a href="https://msdn.microsoft.com/34d0a7e9-4a1e-43ba-a643-800ebaadc360">MouFilter_IsrHook</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543231">PI8042_ISR_WRITE_PORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543252">PI8042_MOUSE_ISR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543263">PI8042_QUEUE_PACKET</a>
 

 

