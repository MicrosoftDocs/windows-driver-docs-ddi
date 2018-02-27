---
UID: NS:ntdd8042._INTERNAL_I8042_HOOK_MOUSE
title: "_INTERNAL_I8042_HOOK_MOUSE"
author: windows-driver-content
description: INTERNAL_I8042_HOOK_MOUSE is used by I8042prt to connect an optional callback routine that supplements the operation of the mouse ISR. The callback can be supplied by an optional, vendor-supplied, upper-level filter driver.
old-location: hid\internal_i8042_hook_mouse.htm
old-project: hid
ms.assetid: 7ac9fc14-9e94-412b-811a-6013d46020a0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PINTERNAL_I8042_HOOK_MOUSE, INTERNAL_I8042_HOOK_MOUSE, INTERNAL_I8042_HOOK_MOUSE structure [Human Input Devices], PINTERNAL_I8042_HOOK_MOUSE, PINTERNAL_I8042_HOOK_MOUSE structure pointer [Human Input Devices], _INTERNAL_I8042_HOOK_MOUSE, hid.internal_i8042_hook_mouse, i8042ref_23133caf-3bd0-4160-8213-899e37b7703e.xml, ntdd8042/INTERNAL_I8042_HOOK_MOUSE, ntdd8042/PINTERNAL_I8042_HOOK_MOUSE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntdd8042.h
api_name:
-	INTERNAL_I8042_HOOK_MOUSE
product: Windows
targetos: Windows
req.typenames: INTERNAL_I8042_HOOK_MOUSE, *PINTERNAL_I8042_HOOK_MOUSE
---

# _INTERNAL_I8042_HOOK_MOUSE structure


## -description


INTERNAL_I8042_HOOK_MOUSE is used by I8042prt to connect an optional callback routine that supplements the operation of the mouse ISR. The callback can be supplied by an optional, vendor-supplied, upper-level filter driver.


## -syntax


````
typedef struct _INTERNAL_I8042_HOOK_MOUSE {
  PVOID                 Context;
  PI8042_MOUSE_ISR      IsrRoutine;
  PI8042_ISR_WRITE_PORT IsrWritePort;
  PI8042_QUEUE_PACKET   QueueMousePacket;
  PVOID                 CallContext;
} INTERNAL_I8042_HOOK_MOUSE, *PINTERNAL_I8042_HOOK_MOUSE;
````


## -struct-fields




### -field Context

Pointer, if non-<b>NULL</b>, to the context that must be used with the <b>IsrRoutine</b> routine. Otherwise, <b>Context</b> is <b>NULL</b>. 


### -field IsrRoutine

Pointer, if non-<b>NULL</b>, to an optional <a href="..\ntdd8042\nc-ntdd8042-pi8042_mouse_isr.md">PI8042_MOUSE_ISR</a> callback that customizes the operation of the I8042prt mouse ISR. Otherwise, <b>IsrRoutine </b>is <b>NULL</b>. 


### -field IsrWritePort

Pointer to the system-supplied mouse <a href="..\ntdd8042\nc-ntdd8042-pi8042_isr_write_port.md">PI8042_ISR_WRITE_PORT</a> callback, which writes data to a mouse.


### -field QueueMousePacket

Pointer to the system-supplied mouse <a href="..\ntdd8042\nc-ntdd8042-pi8042_queue_packet.md">PI8042_QUEUE_PACKET</a> callback, which queues a mouse input data packet for processing by the mouse's ISR deferred procedure call. 


### -field CallContext

Pointer to the context that must be used with the <b>IsrWritePort</b> and <b>QueueMousePacket</b> routines. 


## -remarks



This structure is only used with an <a href="..\ntdd8042\ni-ntdd8042-ioctl_internal_i8042_hook_mouse.md">IOCTL_INTERNAL_I8042_HOOK_MOUSE</a> request. 

<b>Context</b>, <b>InitializationRoutine</b>, and <b>IsrRoutine</b> can be supplied by an optional, vendor-supplied, upper-level filter driver. 

<b>IsrWritePort</b>, <b>QueueMousePacket</b>, and <b>CallContext</b> are supplied by I8042prt.




## -see-also

<a href="..\ntdd8042\ni-ntdd8042-ioctl_internal_i8042_hook_mouse.md">IOCTL_INTERNAL_I8042_HOOK_MOUSE</a>



<a href="..\ntdd8042\nc-ntdd8042-pi8042_queue_packet.md">PI8042_QUEUE_PACKET</a>



<a href="..\ntdd8042\nc-ntdd8042-pi8042_mouse_isr.md">PI8042_MOUSE_ISR</a>



<a href="..\ntdd8042\nc-ntdd8042-pi8042_isr_write_port.md">PI8042_ISR_WRITE_PORT</a>



<a href="https://msdn.microsoft.com/34d0a7e9-4a1e-43ba-a643-800ebaadc360">MouFilter_IsrHook</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20INTERNAL_I8042_HOOK_MOUSE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

