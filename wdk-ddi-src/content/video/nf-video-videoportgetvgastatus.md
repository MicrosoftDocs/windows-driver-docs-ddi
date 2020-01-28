---
UID: NF:video.VideoPortGetVgaStatus
title: VideoPortGetVgaStatus function (video.h)
description: The VideoPortGetVgaStatus function detects whether the calling device is decoding a VGA I/O address.
old-location: display\videoportgetvgastatus.htm
tech.root: display
ms.assetid: 5a2bb69c-b10a-41bb-a92a-de7add3ca2c5
ms.date: 05/10/2018
ms.keywords: VideoPortGetVgaStatus, VideoPortGetVgaStatus function [Display Devices], VideoPort_Functions_f3e43fe4-2e50-48d4-b185-f44e2a2adb31.xml, display.videoportgetvgastatus, video/VideoPortGetVgaStatus
f1_keywords:
 - "video/VideoPortGetVgaStatus"
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortGetVgaStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortGetVgaStatus function

## -description

The <b>VideoPortGetVgaStatus</b> function detects whether the calling device is decoding a VGA I/O address.


## -parameters

### -param HwDeviceExtension

Pointer to the miniport driver's device extension.

### -param VgaStatus [out]

Pointer to the resulting VGA status. A value of zero (0) indicates that VGA is not enabled; a value of one (1) indicates that VGA is enabled.

## -returns

<b>VideoPortGetVgaStatus</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|NO_ERROR|The function completed successfully.|
|ERROR_INVALID_FUNCTION|The device was not a PCI device.|

## -remarks

The <b>VideoPortGetVgaStatus</b> function is mainly used to determine whether a device is the sole VGA-enabled device in a <a href="https://docs.microsoft.com/windows-hardware/drivers/display/multiple-monitor-support-in-the-display-driver">multiple monitor</a> system. 



