---
UID: NI:scsiscan.IOCTL_SCSISCAN_GET_INFO
title: IOCTL_SCSISCAN_GET_INFO
author: windows-driver-content
description: The IOCTL_SCSISCAN_GET_INFO I/O control code returns device information.
old-location: image\ioctl_scsiscan_get_info.htm
old-project: image
ms.assetid: 48045e29-5982-44e6-b9a7-3b000e5cf338
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: image.ioctl_scsiscan_get_info, IOCTL_SCSISCAN_GET_INFO control code [Imaging Devices], IOCTL_SCSISCAN_GET_INFO, scsiscan/IOCTL_SCSISCAN_GET_INFO, stifnc_5897897c-6c10-42cd-9301-d5b5f54675fd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: scsiscan.h
req.include-header: Scsiscan.h
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
-	scsiscan.h
apiname:
-	IOCTL_SCSISCAN_GET_INFO
product: Windows
targetos: Windows
req.typenames: ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
req.product: Windows 10 or later.
---

# IOCTL_SCSISCAN_GET_INFO IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_SCSISCAN_GET_INFO</b> I/O control code returns device information.


## -ioctlparameters




### -input-buffer

Set to NULL.


### -input-buffer-length

Set to 0.


### -output-buffer

Pointer to a <a href="..\scsiscan\ns-scsiscan-_scsiscan_info.md">SCSISCAN_INFO</a> structure.


### -output-buffer-length

Size of output buffer.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



When the DeviceloControl function is called with the <b>IOCTL_SCSISCAN_GET_INFO</b> I/O control code, the caller must specify the address of a SCSISCAN_INFO structure as the function's lpOutbuffer parameter. The kernel-mode driver fills in the structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IOCTL_SCSISCAN_GET_INFO control code%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

