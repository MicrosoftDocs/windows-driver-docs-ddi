---
UID: NI:hidclass.IOCTL_HID_DEVICERESET_NOTIFICATION
title: IOCTL_HID_DEVICERESET_NOTIFICATION
author: windows-driver-content
description: The IOCTL_HID_DEVICERESET_NOTIFICATION request is sent by the HID client driver to HID class driver to wait for a device-initiated reset event.
old-location: hid\ioctl_hid_devicereset_notification.htm
old-project: hid
ms.assetid: 3A9047BE-C974-45E1-89C7-BF0A5F58DD8B
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_HID_DEVICERESET_NOTIFICATION, IOCTL_HID_DEVICERESET_NOTIFICATION control code [Human Input Devices], hid.ioctl_hid_devicereset_notification, hidclass/IOCTL_HID_DEVICERESET_NOTIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidclass.h
req.include-header: Hidclass.h
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
-	hidclass.h
apiname:
-	IOCTL_HID_DEVICERESET_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
---

# IOCTL_HID_DEVICERESET_NOTIFICATION IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_HID_DEVICERESET_NOTIFICATION</b> 
   request is sent by the HID client driver to HID class driver to wait for a device-initiated reset event.

Only one device reset notification request is allowed at any one  time.


## -ioctlparameters




### -input-buffer


       None.


### -input-buffer-length

None.


### -output-buffer


       None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

I<b>rp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 

