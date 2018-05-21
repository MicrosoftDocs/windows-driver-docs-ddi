---
UID: NC:ntdd8042.PI8042_MOUSE_ISR
title: PI8042_MOUSE_ISR
author: windows-driver-content
description: A PI8042_MOUSE_ISR-typed callback routine customizes the operation of the I8042prt mouse ISR.
old-location: hid\pi8042_mouse_isr.htm
old-project: hid
ms.assetid: 7c8a0dc8-49ec-476f-b183-1baa419e831d
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: MouseIsr, MouseIsr callback function [Human Input Devices], PI8042_MOUSE_ISR, PI8042_MOUSE_ISR callback, hid.pi8042_mouse_isr, i8042ref_f077c4e7-f77b-4f47-a0a7-a7007e4f2475.xml, ntdd8042/MouseIsr
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
-	MouseIsr
product:
- Windows
targetos: Windows
req.typenames: 
---

# PI8042_MOUSE_ISR callback function


## -description


A PI8042_MOUSE_ISR-typed callback routine customizes the operation of the I8042prt mouse ISR.


## -parameters




### -param IsrContext [in]

Pointer to the filter device object of the driver that supplies this callback.


### -param CurrentInput [in]

Pointer to the input <a href="https://msdn.microsoft.com/library/windows/hardware/ff542403">MOUSE_INPUT_DATA</a> structure being constructed by the ISR.


### -param CurrentOutput [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff543218">OUTPUT_PACKET</a> structure, which specifies an array of bytes being written to the hardware device.


### -param StatusByte [in]

Specifies a status byte that is read from I/O port 60 when the interrupt occurs.


### -param Byte [in]

Specifies a data byte that is read from I/O port 64 when the interrupt occurs.


### -param ContinueProcessing [in, out]

Specifies, if <b>TRUE</b>, that processing in the I8042prt mouse ISR will continue after this callback completes. Otherwise, processing does not continue.


### -param MouseState [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542405">MOUSE_STATE</a> enumeration value, which identifies the state of mouse input.


### -param ResetSubState [in]

Pointer to MOUSE_RESET_SUBSTATE enumeration value, which identifies the mouse reset substate. See the Remarks section.


## -returns



A PI8042_MOUSE_ISR callback returns <b>TRUE</b> if the I8042prt mouse ISR should continue; otherwise it returns <b>FALSE</b>.




## -remarks



A PI8042_MOUSE_ISR callback is not needed if the default operation of the I8042prt mouse ISR is sufficient.

An upper-level keyboard filter driver can provide a mouse ISR callback. After the I8042prt mouse ISR validates the interrupt, it calls the mouse ISR callback.

To reset a mouse, I8042prt goes through a sequence of operational substates, each one of which is identified by a MOUSE_RESET_SUBSTATE enumeration value. For more information about how I8042prt resets a mouse and the corresponding mouse reset substates, see the documentation of MOUSE_RESET_SUBSTATE in ntdd8042.h.

A PI8042_MOUSE_ISR callback runs in kernel mode at the IRQL of the I8042prt mouse ISR.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542403">MOUSE_INPUT_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542405">MOUSE_STATE</a>



<a href="https://msdn.microsoft.com/34d0a7e9-4a1e-43ba-a643-800ebaadc360">MouFilter_IsrHook</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543218">OUTPUT_PACKET</a>
 

 

