---
UID: NC:ntdd8042.PI8042_KEYBOARD_ISR
title: PI8042_KEYBOARD_ISR
author: windows-driver-content
description: A PI8042_KEYBOARD_ISR-typed callback routine customizes the operation of the I8042prt keyboard ISR.
old-location: hid\pi8042_keyboard_isr.htm
old-project: hid
ms.assetid: e21fa089-0650-4a3f-96f9-f479d36ef080
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hid.pi8042_keyboard_isr, KeyboardIsr callback function [Human Input Devices], KeyboardIsr, PI8042_KEYBOARD_ISR, PI8042_KEYBOARD_ISR, ntdd8042/KeyboardIsr, i8042ref_34293f47-3e6c-4721-ab58-8ac531543c8e.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ntdd8042.h
apiname:
-	KeyboardIsr
product: Windows
targetos: Windows
req.typenames: "*PMIRACAST_DRIVER_INTERFACE, MIRACAST_DRIVER_INTERFACE"
---

# PI8042_KEYBOARD_ISR callback


## -description


A PI8042_KEYBOARD_ISR-typed callback routine customizes the operation of the I8042prt keyboard ISR.


## -prototype


````
PI8042_KEYBOARD_ISR KeyboardIsr;

BOOLEAN KeyboardIsr(
  _In_  PVOID                IsrContext,
  _In_  PKEYBOARD_INPUT_DATA CurrentInput,
  _In_  POUTPUT_PACKET       CurrentOutput,
  _In_  UCHAR                StatusByte,
  _In_  PUCHAR               Byte,
  _Out_ PBOOLEAN             ContinueProcessing,
  _In_  PKEYBOARD_SCAN_STATE ScanState
)
{ ... }
````


## -parameters




### -param IsrContext [in]

Pointer to the filter device object of the driver that supplies a callback.


### -param CurrentInput [in]

Pointer to the input <a href="https://msdn.microsoft.com/library/windows/hardware/ff542337">KEYBOARD_INPUT_DATA</a> structure that is being constructed by the ISR.


### -param CurrentOutput [in]

Pointer to an <a href="..\ntdd8042\ns-ntdd8042-_output_packet.md">OUTPUT_PACKET</a> structure, which specifies an array of bytes that is being written to the hardware device.


### -param StatusByte [in]

Specifies the status byte that is read from I/O port 60 when an interrupt occurs.


### -param Byte [in]

Specifies the data byte that is read  from I/O port 64 when an interrupt occurs.


### -param ContinueProcessing [out]

Specifies, if <b>TRUE</b>, that processing in the I8042prt keyboard ISR will continue after this callback completes. Otherwise, processing does not continue.


### -param ScanState [in]

Pointer to a <a href="..\ntdd8042\ne-ntdd8042-_keyboard_scan_state.md">KEYBOARD_SCAN_STATE</a> enumeration value, which identifies the keyboard scan state.


## -returns


A PI8042_KEYBOARD_ISR callback returns <b>TRUE</b> if the I8042prt keyboard ISR should continue; otherwise it returns <b>FALSE</b>.



## -remarks


A PI8042_KEYBOARD_ISR callback is not needed if the default operation of the I8042prt keyboard ISR is sufficient. 

An optional, vendor-supplied, upper-level keyboard filter driver can provide a PI8042_KEYBOARD_ISR callback. The I8042prt ISR calls the callback after it validates the interrupt and reads the scan code. 

The PI8042_KEYBOARD_ISR callback runs in kernel mode at the IRQL of the I8042prt keyboard ISR.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542337">KEYBOARD_INPUT_DATA</a>

<a href="..\ntdd8042\ne-ntdd8042-_keyboard_scan_state.md">KEYBOARD_SCAN_STATE</a>

<a href="https://msdn.microsoft.com/0feca7de-aa80-4d1e-a5fc-901c18169649">KbFilter_IsrHook</a>

<a href="..\ntdd8042\ns-ntdd8042-_output_packet.md">OUTPUT_PACKET</a>

<a href="..\ntdd8042\nc-ntdd8042-pi8042_keyboard_isr.md">PI8042_KEYBOARD_ISR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20PI8042_KEYBOARD_ISR callback function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

