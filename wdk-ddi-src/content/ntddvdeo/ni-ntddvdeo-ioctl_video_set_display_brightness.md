---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS
title: IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS
author: windows-driver-content
description: This IOCTL is not handled by video miniport drivers. It is handled entirely by the system-supplied video port driver.
old-location: display\ioctl_video_set_display_brightness.htm
old-project: display
ms.assetid: 485119b4-90f8-44dc-89d7-afb536442719
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS, IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS control, IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS control code [Display Devices], Video_IOCTLs_3dc31eac-247b-400e-8202-c0708086326c.xml, display.ioctl_video_set_display_brightness, ntddvdeo/IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS
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
-	IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS IOCTL


## -description



This IOCTL is not handled by video miniport drivers. It is handled entirely by the system-supplied video port driver.




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

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).




## -remarks



<div class="alert"><b>Note</b>    This IOCTL is obsolete in Windows Vista. Instead, use the Windows Management Instrumentation (WMI) <b>WmiMonitorBrightnessMethods</b> class. For information about WMI, see the documentation in the Microsoft Windows SDK.</div>
<div> </div>


