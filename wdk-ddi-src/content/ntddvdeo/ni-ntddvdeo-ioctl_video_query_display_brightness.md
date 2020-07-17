---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_DISPLAY_BRIGHTNESS
title: IOCTL_VIDEO_QUERY_DISPLAY_BRIGHTNESS (ntddvdeo.h)
description: This IOCTL is not handled by video miniport drivers. It is handled entirely by the system-supplied video port driver.
old-location: display\ioctl_video_query_display_brightness.htm
tech.root: display
ms.assetid: 8dccc5bd-c678-4c94-9fa6-c5ac37ad6d0e
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_QUERY_DISPLAY_BRIGHTNESS IOCTL"]
ms.keywords: IOCTL_VIDEO_QUERY_DISPLAY_BRIGHTNESS, IOCTL_VIDEO_QUERY_DISPLAY_BRIGHTNESS control, IOCTL_VIDEO_QUERY_DISPLAY_BRIGHTNESS control code [Display Devices], Video_IOCTLs_f55cce8d-9a8e-45ef-98e2-8cabc27cd9e6.xml, display.ioctl_video_query_display_brightness, ntddvdeo/IOCTL_VIDEO_QUERY_DISPLAY_BRIGHTNESS
f1_keywords:
 - "ntddvdeo/IOCTL_VIDEO_QUERY_DISPLAY_BRIGHTNESS"
 - "IOCTL_VIDEO_QUERY_DISPLAY_BRIGHTNESS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddvdeo.h
api_name:
- IOCTL_VIDEO_QUERY_DISPLAY_BRIGHTNESS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_QUERY_DISPLAY_BRIGHTNESS IOCTL


## -description



This IOCTL is not handled by video miniport drivers. It is handled entirely by the system-supplied video port driver.




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

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).




## -remarks



<div class="alert"><b>Note</b>    This IOCTL is obsolete in Windows Vista. Instead, use the Windows Management Instrumentation (WMI) monitor brightness class. For information about WMI, see the documentation in the Microsoft Windows SDK.</div>
<div> </div>


