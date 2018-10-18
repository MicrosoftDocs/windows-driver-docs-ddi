---
UID: NS:ntdd8042._INTERNAL_I8042_HOOK_KEYBOARD
title: "_INTERNAL_I8042_HOOK_KEYBOARD"
author: windows-driver-content
description: INTERNAL_I8042_HOOK_KEYBOARD is used by I8042prt to connect optional callback routines that supplement keyboard initialization and the keyboard ISR. The callbacks can be supplied by an optional, vendor-supplied, upper-level filter driver.
old-location: hid\internal_i8042_hook_keyboard.htm
tech.root: hid
ms.assetid: 7a70f6e1-cf3b-4158-97f2-39f62a1d51ae
ms.date: 4/30/2018
ms.keywords: "*PINTERNAL_I8042_HOOK_KEYBOARD, INTERNAL_I8042_HOOK_KEYBOARD, INTERNAL_I8042_HOOK_KEYBOARD structure [Human Input Devices], PINTERNAL_I8042_HOOK_KEYBOARD, PINTERNAL_I8042_HOOK_KEYBOARD structure pointer [Human Input Devices], _INTERNAL_I8042_HOOK_KEYBOARD, hid.internal_i8042_hook_keyboard, i8042ref_c61fafd5-75ed-484b-8f5a-9e5e526059af.xml, ntdd8042/INTERNAL_I8042_HOOK_KEYBOARD, ntdd8042/PINTERNAL_I8042_HOOK_KEYBOARD"
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
-	INTERNAL_I8042_HOOK_KEYBOARD
product:
- Windows
targetos: Windows
req.typenames: INTERNAL_I8042_HOOK_KEYBOARD, *PINTERNAL_I8042_HOOK_KEYBOARD
---

# _INTERNAL_I8042_HOOK_KEYBOARD structure


## -description


INTERNAL_I8042_HOOK_KEYBOARD is used by I8042prt to connect optional callback routines that supplement keyboard initialization and the keyboard ISR. The callbacks can be supplied by an optional, vendor-supplied, upper-level filter driver.


## -struct-fields




### -field Context

Pointer, if non-<b>NULL</b>, to the context that must be used with the <b>InitializationRoutine</b> and <b>IsrRoutine</b> routines. Otherwise, <b>Context</b> is <b>NULL</b>. 


### -field InitializationRoutine

Pointer, if non-<b>NULL</b>, to an optional <a href="https://msdn.microsoft.com/library/windows/hardware/ff543243">PI8042_KEYBOARD_INITIALIZATION_ROUTINE</a>callback. I8042prt uses this callback to initialize a device after the device is reset. Otherwise, <b>IntializatonRoutine</b> is <b>NULL</b>.


### -field IsrRoutine

Pointer, if non-<b>NULL</b>, to an optional <a href="https://msdn.microsoft.com/library/windows/hardware/ff543248">PI8042_KEYBOARD_ISR</a> callback that customizes the operation of the I8042prt keyboard ISR. Otherwise, <b>IsrRoutine </b>is <b>NULL</b>.


### -field IsrWritePort

Pointer to the system-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff543231">PI8042_ISR_WRITE_PORT</a> callback, which writes data to a keyboard.


### -field QueueKeyboardPacket

Pointer to the system-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff543263">PI8042_QUEUE_PACKET</a> callback, which queues a keyboard input data packet for processing by the keyboard's ISR deferred procedure call.


### -field CallContext

Pointer to the context that must be used with the <b>IsrWritePort</b> and <b>QueueKeyboardPacket</b> routines. 


## -remarks



This structure is only used with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541238">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a> request. 

<b>Context</b>, <b>InitializationRoutine</b>, and <b>IsrRoutine</b> can be supplied by an optional, vendor-supplied, upper-level filter driver.

<b>IsrWritePort</b>, <b>QueueKeyboardPacket</b>, and <b>CallContext</b> are supplied by I8042prt.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541238">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a>



<a href="https://msdn.microsoft.com/1ea0ce84-f3e3-48af-8015-66fc35c17129">KbFilter_InitializationRoutine</a>



<a href="https://msdn.microsoft.com/0feca7de-aa80-4d1e-a5fc-901c18169649">KbFilter_IsrHook</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543231">PI8042_ISR_WRITE_PORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543248">PI8042_KEYBOARD_ISR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543263">PI8042_QUEUE_PACKET</a>
 

 

