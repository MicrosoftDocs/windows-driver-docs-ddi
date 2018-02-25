---
UID: NI:ntdd8042.IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION
title: IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION
author: windows-driver-content
description: The IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION request passes a pointer to a mouse interrupt object.
old-location: hid\ioctl_internal_i8042_mouse_start_information.htm
old-project: hid
ms.assetid: aa7d5802-d1d0-4c7c-bf55-0f0b5b664113
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION, IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION control code [Human Input Devices], hid.ioctl_internal_i8042_mouse_start_information, i8042ref_c4c81870-f104-4979-86e3-03bd376e34ce.xml, ntdd8042/IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntdd8042.h
apiname:
-	IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION
product: Windows
targetos: Windows
req.typenames: MOUSE_STATE, *PMOUSE_STATE
---

# IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



The IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION request passes a pointer to a mouse interrupt object. I8042prt sends this request synchronously to the top of the device stack after the mouse interrupt object is created. Upper-level filter drivers that need to synchronize their callback operation with the mouse ISR can use the pointer to the mouse interrupt object.




## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.Type3InputBuffer</b> points to an input buffer allocated by I8042prt to input an <a href="..\ntdd8042\ns-ntdd8042-_internal_i8042_start_information.md">INTERNAL_I8042_START_INFORMATION</a> structure.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> specifies the size, in bytes, of an INTERNAL_I8042_START_INFORMATION structure.


### -output-buffer

None


### -output-buffer-length

None


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to STATUS_SUCCESS.


## -see-also

<a href="..\ntdd8042\ns-ntdd8042-_internal_i8042_start_information.md">INTERNAL_I8042_START_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

