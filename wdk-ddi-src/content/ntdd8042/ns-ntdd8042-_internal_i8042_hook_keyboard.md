---
UID: NS:ntdd8042._INTERNAL_I8042_HOOK_KEYBOARD
title: "_INTERNAL_I8042_HOOK_KEYBOARD"
author: windows-driver-content
description: INTERNAL_I8042_HOOK_KEYBOARD is used by I8042prt to connect optional callback routines that supplement keyboard initialization and the keyboard ISR. The callbacks can be supplied by an optional, vendor-supplied, upper-level filter driver.
old-location: hid\internal_i8042_hook_keyboard.htm
old-project: hid
ms.assetid: 7a70f6e1-cf3b-4158-97f2-39f62a1d51ae
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: "_INTERNAL_I8042_HOOK_KEYBOARD, ntdd8042/PINTERNAL_I8042_HOOK_KEYBOARD, hid.internal_i8042_hook_keyboard, INTERNAL_I8042_HOOK_KEYBOARD, *PINTERNAL_I8042_HOOK_KEYBOARD, PINTERNAL_I8042_HOOK_KEYBOARD, PINTERNAL_I8042_HOOK_KEYBOARD structure pointer [Human Input Devices], INTERNAL_I8042_HOOK_KEYBOARD structure [Human Input Devices], i8042ref_c61fafd5-75ed-484b-8f5a-9e5e526059af.xml, ntdd8042/INTERNAL_I8042_HOOK_KEYBOARD"
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
-	INTERNAL_I8042_HOOK_KEYBOARD
product: Windows
targetos: Windows
req.typenames: INTERNAL_I8042_HOOK_KEYBOARD, *PINTERNAL_I8042_HOOK_KEYBOARD
---

# _INTERNAL_I8042_HOOK_KEYBOARD structure


## -description


INTERNAL_I8042_HOOK_KEYBOARD is used by I8042prt to connect optional callback routines that supplement keyboard initialization and the keyboard ISR. The callbacks can be supplied by an optional, vendor-supplied, upper-level filter driver.


## -syntax


````
typedef struct _INTERNAL_I8042_HOOK_KEYBOARD {
  PVOID                                  Context;
  PI8042_KEYBOARD_INITIALIZATION_ROUTINE InitializationRoutine;
  PI8042_KEYBOARD_ISR                    IsrRoutine;
  PI8042_ISR_WRITE_PORT                  IsrWritePort;
  PI8042_QUEUE_PACKET                    QueueKeyboardPacket;
  PVOID                                  CallContext;
} INTERNAL_I8042_HOOK_KEYBOARD, *PINTERNAL_I8042_HOOK_KEYBOARD;
````


## -struct-fields




#### - Context

Pointer, if non-<b>NULL</b>, to the context that must be used with the <b>InitializationRoutine</b> and <b>IsrRoutine</b> routines. Otherwise, <b>Context</b> is <b>NULL</b>. 


#### - InitializationRoutine

Pointer, if non-<b>NULL</b>, to an optional <a href="..\ntdd8042\nc-ntdd8042-pi8042_keyboard_initialization_routine.md">PI8042_KEYBOARD_INITIALIZATION_ROUTINE</a>callback. I8042prt uses this callback to initialize a device after the device is reset. Otherwise, <b>IntializatonRoutine</b> is <b>NULL</b>.


#### - IsrRoutine

Pointer, if non-<b>NULL</b>, to an optional <a href="..\ntdd8042\nc-ntdd8042-pi8042_keyboard_isr.md">PI8042_KEYBOARD_ISR</a> callback that customizes the operation of the I8042prt keyboard ISR. Otherwise, <b>IsrRoutine </b>is <b>NULL</b>.


#### - IsrWritePort

Pointer to the system-supplied <a href="..\ntdd8042\nc-ntdd8042-pi8042_isr_write_port.md">PI8042_ISR_WRITE_PORT</a> callback, which writes data to a keyboard.


#### - QueueKeyboardPacket

Pointer to the system-supplied <a href="..\ntdd8042\nc-ntdd8042-pi8042_queue_packet.md">PI8042_QUEUE_PACKET</a> callback, which queues a keyboard input data packet for processing by the keyboard's ISR deferred procedure call.


#### - CallContext

Pointer to the context that must be used with the <b>IsrWritePort</b> and <b>QueueKeyboardPacket</b> routines. 


## -remarks


This structure is only used with an <a href="..\ntdd8042\ni-ntdd8042-ioctl_internal_i8042_hook_keyboard.md">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a> request. 

<b>Context</b>, <b>InitializationRoutine</b>, and <b>IsrRoutine</b> can be supplied by an optional, vendor-supplied, upper-level filter driver.

<b>IsrWritePort</b>, <b>QueueKeyboardPacket</b>, and <b>CallContext</b> are supplied by I8042prt.



## -see-also

<a href="..\ntdd8042\ni-ntdd8042-ioctl_internal_i8042_hook_keyboard.md">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a>

<a href="https://msdn.microsoft.com/0feca7de-aa80-4d1e-a5fc-901c18169649">KbFilter_IsrHook</a>

<a href="..\ntdd8042\nc-ntdd8042-pi8042_isr_write_port.md">PI8042_ISR_WRITE_PORT</a>

<a href="..\ntdd8042\nc-ntdd8042-pi8042_keyboard_isr.md">PI8042_KEYBOARD_ISR</a>

<a href="..\ntdd8042\nc-ntdd8042-pi8042_queue_packet.md">PI8042_QUEUE_PACKET</a>

<a href="https://msdn.microsoft.com/1ea0ce84-f3e3-48af-8015-66fc35c17129">KbFilter_InitializationRoutine</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20INTERNAL_I8042_HOOK_KEYBOARD structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

