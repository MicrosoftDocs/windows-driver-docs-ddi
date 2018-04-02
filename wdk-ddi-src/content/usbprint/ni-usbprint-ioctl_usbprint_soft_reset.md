---
UID: NI:usbprint.IOCTL_USBPRINT_SOFT_RESET
title: IOCTL_USBPRINT_SOFT_RESET
author: windows-driver-content
description: The IOCTL_USBPRINT_SOFT_RESET request allows upper-layer software (such as a language monitor), to issue a class-specific soft reset command to the printer.
old-location: print\ioctl_usbprint_soft_reset.htm
old-project: print
ms.assetid: 84e9197a-a096-42ff-af0d-3f4dab9fe0c6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_USBPRINT_SOFT_RESET, IOCTL_USBPRINT_SOFT_RESET control code [Print Devices], print.ioctl_usbprint_soft_reset, usbioctl_282627ce-49eb-4d8c-88a6-8d211cb91830.xml, usbprint/IOCTL_USBPRINT_SOFT_RESET
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
-	IOCTL_USBPRINT_SOFT_RESET
product:
- Windows
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION
req.product: Windows 10 or later.
---

# IOCTL_USBPRINT_SOFT_RESET IOCTL


## -description


The <b>IOCTL_USBPRINT_SOFT_RESET</b> request allows upper-layer software (such as a language monitor), to issue a class-specific soft reset command to the printer.


## -ioctlparameters




### -input-buffer

Not used with this operation; set this parameter to <b>NULL</b>.


### -input-buffer-length

Not used with this operation; set this parameter to 0.


### -output-buffer

Not used with this operation; set this parameter to <b>NULL</b>.


### -output-buffer-length

Not used with this operation; set this parameter to 0.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

