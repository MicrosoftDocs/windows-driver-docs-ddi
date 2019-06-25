---
UID: NC:ntdd8042.PI8042_ISR_WRITE_PORT
title: PI8042_ISR_WRITE_PORT (ntdd8042.h)
description: The PI8042_ISR_WRITE_PORT-typed callback routine writes data to an i8042 port. I8042prt provides this callback.
old-location: hid\pi8042_isr_write_port.htm
tech.root: hid
ms.assetid: deded3fb-f0b3-4af5-b8b4-03658293b0fc
ms.date: 04/30/2018
ms.keywords: I8042IsrWritePort, I8042IsrWritePort callback function [Human Input Devices], PI8042_ISR_WRITE_PORT, PI8042_ISR_WRITE_PORT callback, hid.pi8042_isr_write_port, i8042ref_775d438e-5883-455b-86c4-2ce28099598f.xml, ntdd8042/I8042IsrWritePort
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ntdd8042.h
api_name:
- I8042IsrWritePort
product:
- Windows
targetos: Windows
req.typenames: 
---

# PI8042_ISR_WRITE_PORT callback function


## -description


The PI8042_ISR_WRITE_PORT-typed callback routine writes data to an i8042 port. I8042prt provides this callback.


## -parameters




### -param Context [in]

Pointer to the function device object that represents a keyboard or mouse device.


### -param Value [in]

Specifies the data to write to an i8042 port.


## -returns



None




## -remarks



The PI8042_ISR_WRITE_PORT callback should only be called by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdd8042/nc-ntdd8042-pi8042_keyboard_isr">PI8042_KEYBOARD_ISR</a> callback or a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdd8042/nc-ntdd8042-pi8042_mouse_isr">PI8042_MOUSE_ISR</a> callback. I8042prt calls a vendor-supplied ISR callback for a device in the corresponding I8042prt device ISR.

I8042prt specifies the keyboard write port callback in the <b>IsrWritePort</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdd8042/ns-ntdd8042-_internal_i8042_hook_keyboard">INTERNAL_I8042_HOOK_KEYBOARD</a> structure that I8042prt uses with an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdd8042/ni-ntdd8042-ioctl_internal_i8042_hook_keyboard">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a> request.

I8042prt specifies the mouse write port callback in the <b>IsrWritePort</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdd8042/ns-ntdd8042-_internal_i8042_hook_mouse">INTERNAL_I8042_HOOK_MOUSE</a> structure that I8042prt uses with an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdd8042/ni-ntdd8042-ioctl_internal_i8042_hook_keyboard">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a> request.

The PI8042_ISR_WRITE_PORT callback runs in kernel mode at the same IRQL as the I8042prt ISR for the device.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdd8042/ns-ntdd8042-_internal_i8042_hook_mouse">INTERNAL_I8042_HOOK_MOUSE</a>



<b>IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdd8042/ni-ntdd8042-ioctl_internal_i8042_hook_mouse">IOCTL_INTERNAL_I8042_HOOK_MOUSE</a>
 

 

