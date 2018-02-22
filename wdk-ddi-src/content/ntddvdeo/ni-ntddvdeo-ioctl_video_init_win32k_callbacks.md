---
UID: NI:ntddvdeo.IOCTL_VIDEO_INIT_WIN32K_CALLBACKS
title: IOCTL_VIDEO_INIT_WIN32K_CALLBACKS
author: windows-driver-content
description: This IOCTL is for internal use only.
old-location: display\ioctl_video_init_win32k_callbacks.htm
old-project: display
ms.assetid: 1b003614-e80c-459d-a315-0dfdabcec5cc
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.ioctl_video_init_win32k_callbacks, IOCTL_VIDEO_INIT_WIN32K_CALLBACKS control code [Display Devices], IOCTL_VIDEO_INIT_WIN32K_CALLBACKS, ntddvdeo/IOCTL_VIDEO_INIT_WIN32K_CALLBACKS, Video_IOCTLs_b482cd12-bd15-47b4-ba9c-fca652800d62.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddvdeo.h
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
-	Ntddvdeo.h
apiname:
-	IOCTL_VIDEO_INIT_WIN32K_CALLBACKS
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_INIT_WIN32K_CALLBACKS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

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



