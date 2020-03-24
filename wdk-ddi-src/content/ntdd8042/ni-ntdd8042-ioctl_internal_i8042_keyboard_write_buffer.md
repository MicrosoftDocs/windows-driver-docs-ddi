---
UID: NI:ntdd8042.IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER
title: IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER (ntdd8042.h)
description: The IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER request writes data to the i8042 port controller to control operation of a keyboard device.
old-location: hid\ioctl_internal_i8042_keyboard_write_buffer.htm
tech.root: hid
ms.assetid: 583263fc-8b95-47d9-9f20-306b2200b573
ms.date: 04/30/2018
keywords: ["IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER IOCTL"]
ms.keywords: IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER, IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER control, IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER control code [Human Input Devices], hid.ioctl_internal_i8042_keyboard_write_buffer, i8042ref_a981431f-38cd-4cc4-899e-a79799da0e01.xml, ntdd8042/IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER
f1_keywords:
 - "ntdd8042/IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntdd8042.h
api_name:
- IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER IOCTL


## -description



The IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER request writes data to the i8042 port controller to control operation of a keyboard device. A filter driver can use this request to control the operation of a keyboard.

I8042prt synchronizes write buffer requests and other keyboard requests that write to the i8042 port controller, including <a href="https://docs.microsoft.com/windows/desktop/api/ntddkbd/ni-ntddkbd-ioctl_keyboard_set_indicators">IOCTL_KEYBOARD_SET_INDICATORS</a> and <a href="https://docs.microsoft.com/windows/desktop/api/ntddkbd/ni-ntddkbd-ioctl_keyboard_set_typematic">IOCTL_KEYBOARD_SET_TYPEMATIC</a>. I8042prt synchronizes the actual write of data with the keyboard ISR.




## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.Type3InputBuffer</b> points to a client-allocated buffer which inputs the data to write to an i8042 port controller.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> is set to the number of bytes in the input buffer, which must be greater than one.


### -output-buffer

None


### -output-buffer-length

None


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Status</b> member is set to one of the following values:




#### -STATUS_DEVICE_NOT_READY

The keyboard interrupt is not initialized.


#### -STATUS_INVALID_PARAMETER

The input parameters are not valid.


#### -STATUS_IO_TIMEOUT

The request timed out.


#### -STATUS_SUCCESS

The request completed successfully.


## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntddkbd/ni-ntddkbd-ioctl_keyboard_set_indicators">IOCTL_KEYBOARD_SET_INDICATORS</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntddkbd/ni-ntddkbd-ioctl_keyboard_set_typematic">IOCTL_KEYBOARD_SET_TYPEMATIC</a>
 

 

