---
UID: NI:usbprint.IOCTL_USBPRINT_SOFT_RESET
title: IOCTL_USBPRINT_SOFT_RESET
author: windows-driver-content
description: The IOCTL_USBPRINT_SOFT_RESET request allows upper-layer software (such as a language monitor), to issue a class-specific soft reset command to the printer.
old-location: print\ioctl_usbprint_soft_reset.htm
old-project: print
ms.assetid: 84e9197a-a096-42ff-af0d-3f4dab9fe0c6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: print.ioctl_usbprint_soft_reset, IOCTL_USBPRINT_SOFT_RESET control code [Print Devices], IOCTL_USBPRINT_SOFT_RESET, usbprint/IOCTL_USBPRINT_SOFT_RESET, usbioctl_282627ce-49eb-4d8c-88a6-8d211cb91830.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbprint.h
apiname:
-	IOCTL_USBPRINT_SOFT_RESET
product: Windows
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION
req.product: Windows 10 or later.
---

# IOCTL_USBPRINT_SOFT_RESET IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

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

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IOCTL_USBPRINT_SOFT_RESET control code%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

