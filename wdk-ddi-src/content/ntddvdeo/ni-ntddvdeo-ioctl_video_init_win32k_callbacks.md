---
UID: NI:ntddvdeo.IOCTL_VIDEO_INIT_WIN32K_CALLBACKS
title: IOCTL_VIDEO_INIT_WIN32K_CALLBACKS
author: windows-driver-content
description: This IOCTL is for internal use only.
old-location: display\ioctl_video_init_win32k_callbacks.htm
old-project: display
ms.assetid: 1b003614-e80c-459d-a315-0dfdabcec5cc
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IOCTL_VIDEO_INIT_WIN32K_CALLBACKS, IOCTL_VIDEO_INIT_WIN32K_CALLBACKS control, IOCTL_VIDEO_INIT_WIN32K_CALLBACKS control code [Display Devices], Video_IOCTLs_b482cd12-bd15-47b4-ba9c-fca652800d62.xml, display.ioctl_video_init_win32k_callbacks, ntddvdeo/IOCTL_VIDEO_INIT_WIN32K_CALLBACKS
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddvdeo.h
api_name:
-	IOCTL_VIDEO_INIT_WIN32K_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_INIT_WIN32K_CALLBACKS IOCTL


## -description



This IOCTL is for internal use only.




## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).



