---
UID: NI:ntdd8042.IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION
title: IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION
author: windows-driver-content
description: The IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION request passes a pointer to a keyboard interrupt object.
old-location: hid\ioctl_internal_i8042_keyboard_start_information.htm
tech.root: hid
ms.assetid: a589b1e1-7462-4de7-83df-c3d55fa01b76
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION, IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION control, IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION control code [Human Input Devices], hid.ioctl_internal_i8042_keyboard_start_information, i8042ref_d5599642-48b8-4b77-b4bb-6e0d7596045d.xml, ntdd8042/IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION IOCTL


## -description



The IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION request passes a pointer to a keyboard interrupt object. I8042prt sends this request synchronously to the top of the device stack after the keyboard interrupt object is created. Upper-level filter drivers that need to synchronize their callback operation with the I8042prt keyboard ISR can use the pointer to the keyboard interrupt object.




## -ioctlparameters




### -input-buffer

<b>AssociatedIrp.SystemBuffer</b> points to a buffer allocated by I8042prt to input an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541052">INTERNAL_I8042_START_INFORMATION</a> structure.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> specifies the size, in bytes, of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541052">INTERNAL_I8042_START_INFORMATION</a> structure.


### -output-buffer

None


### -output-buffer-length

None


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to STATUS_SUCCESS.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541052">INTERNAL_I8042_START_INFORMATION</a>
 

 

