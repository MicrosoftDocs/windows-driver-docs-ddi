---
UID: NI:usbprint.IOCTL_USBPRINT_GET_1284_ID
title: IOCTL_USBPRINT_GET_1284_ID
author: windows-driver-content
description: The IOCTL_USBPRINT_GET_1284_ID control code allows upper-layer software (such as a language monitor), to request and obtain the printer's IEEE 1284 device ID string.
old-location: print\ioctl_usbprint_get_1284_id.htm
old-project: print
ms.assetid: b5c5a0e4-0fd9-4950-ac38-4bf58a0af077
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_USBPRINT_GET_1284_ID, IOCTL_USBPRINT_GET_1284_ID control code [Print Devices], print.ioctl_usbprint_get_1284_id, usbioctl_4b1e9092-6483-4603-b690-a5e655a73670.xml, usbprint/IOCTL_USBPRINT_GET_1284_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbprint.h
req.include-header: 
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
-	usbprint.h
api_name:
-	IOCTL_USBPRINT_GET_1284_ID
product: Windows
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION
req.product: Windows 10 or later.
---

# IOCTL_USBPRINT_GET_1284_ID IOCTL


## -description


The <b>IOCTL_USBPRINT_GET_1284_ID</b> control code allows upper-layer software (such as a language monitor), to request and obtain the printer's IEEE 1284 device ID string.


## -ioctlparameters




### -input-buffer

Not used in this operation; set this parameter to <b>NULL</b>.


### -input-buffer-length

Not used in this operation; set this parameter to 0.


### -output-buffer

The output buffer will contain UCHAR data. On success this buffer can hold the following: a two-byte prefix that specifies the size, in bytes, of the device's IEEE 1284 device ID; the device ID; and a null terminator. An IEEE 1284 device ID can be up to 64 KB in size. On failure, if <b>GetLastError</b>returns the error code <b>STATUS_BUFFER_TOO_SMALL</b>, the output buffer was not large enough to hold the data intended for it.


### -output-buffer-length

The output buffer must be large enough to contain a two-byte quantity holding the length of the device's IEEE 1284 device ID, the device ID (up to 64 KB in size), and a terminating null.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



 

 


