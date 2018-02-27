---
UID: NI:ntddvdeo.IOCTL_VIDEO_PREPARE_FOR_EARECOVERY
title: IOCTL_VIDEO_PREPARE_FOR_EARECOVERY
author: windows-driver-content
description: This IOCTL is for internal use only.
old-location: display\ioctl_video_prepare_for_earecovery.htm
old-project: display
ms.assetid: 71cd4559-9cb3-468e-a53e-fb40b97a90b6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_VIDEO_PREPARE_FOR_EARECOVERY, IOCTL_VIDEO_PREPARE_FOR_EARECOVERY control code [Display Devices], Video_IOCTLs_72bcebdd-6335-4953-9a23-00061760b4a4.xml, display.ioctl_video_prepare_for_earecovery, ntddvdeo/IOCTL_VIDEO_PREPARE_FOR_EARECOVERY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
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
-	Ntddvdeo.h
api_name:
-	IOCTL_VIDEO_PREPARE_FOR_EARECOVERY
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_PREPARE_FOR_EARECOVERY IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



This IOCTL is for internal use only.




## -ioctlparameters




### -input-buffer



<text></text>




### -input-buffer-length



<text></text>




### -output-buffer



<text></text>




### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [XREF-LINK:NTSTATUS Values].



