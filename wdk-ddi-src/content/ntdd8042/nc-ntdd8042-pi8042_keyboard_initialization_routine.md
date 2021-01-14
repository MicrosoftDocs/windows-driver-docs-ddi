---
UID: NC:ntdd8042.PI8042_KEYBOARD_INITIALIZATION_ROUTINE
title: PI8042_KEYBOARD_INITIALIZATION_ROUTINE (ntdd8042.h)
description: A PI8042_KEYBOARD_INITIALIZATION_ROUTINE-typed callback routine supplements the default initialization of a keyboard device by I8042prt.
old-location: hid\pi8042_keyboard_initialization_routine.htm
tech.root: hid
ms.date: 04/30/2018
keywords: ["PI8042_KEYBOARD_INITIALIZATION_ROUTINE callback function"]
ms.keywords: KeyboardInitializationRoutine, KeyboardInitializationRoutine callback function [Human Input Devices], PI8042_KEYBOARD_INITIALIZATION_ROUTINE, PI8042_KEYBOARD_INITIALIZATION_ROUTINE callback, hid.pi8042_keyboard_initialization_routine, i8042ref_4bc54efc-bd3d-4091-a8c7-64631d187d20.xml, ntdd8042/KeyboardInitializationRoutine
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PI8042_KEYBOARD_INITIALIZATION_ROUTINE
 - ntdd8042/PI8042_KEYBOARD_INITIALIZATION_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ntdd8042.h
api_name:
 - PI8042_KEYBOARD_INITIALIZATION_ROUTINE
---

# PI8042_KEYBOARD_INITIALIZATION_ROUTINE callback function


## -description

A PI8042_KEYBOARD_INITIALIZATION_ROUTINE-typed callback routine supplements the default initialization of a keyboard device by I8042prt.

## -parameters

### -param InitializationContext 

[in]
Pointer to the filter device object of the driver that supplies the callback.

### -param SynchFuncContext 

[in]
Pointer to the context for the callbacks that are pointed to by <i>ReadPort</i> and <i>Writeport.</i>

### -param ReadPort 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/ntdd8042/nc-ntdd8042-pi8042_synch_read_port">PI8042_SYNCH_READ_PORT</a> callback that reads from the port.

### -param WritePort 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/ntdd8042/nc-ntdd8042-pi8042_synch_write_port">PI8042_SYNCH_WRITE_PORT</a> callback that writes to the port.

### -param TurnTranslationOn 

[out]
Specifies whether to turn translation on or off. If <i>TranslationOn</i> is <b>TRUE</b>, translation is turned on; otherwise, translation is turned off.

## -returns

A PI8042_KEYBOARD_INITIALIZATION_ROUTINE callback returns an appropriate NTSTATUS code.

## -remarks

An upper-level keyboard filter driver can provide a PI8042_KEYBOARD_INITIALIZATION_ROUTINE callback.

If an upper-level keyboard filter driver supplies an initialization callback, I8042prt calls the filter initialization callback when I8042prt initializes the keyboard. Default keyboard initialization includes the following operations: reset the keyboard, set the typematic rate and delay, and set the light-emitting diodes (LED).

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdd8042/nc-ntdd8042-pi8042_synch_read_port">PI8042_SYNCH_READ_PORT</a>



<a href="/windows-hardware/drivers/ddi/ntdd8042/nc-ntdd8042-pi8042_synch_write_port">PI8042_SYNCH_WRITE_PORT</a>

