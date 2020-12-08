---
UID: NF:video.VideoPortGetVersion
title: VideoPortGetVersion function (video.h)
description: The VideoPortGetVersion function gets version information about the currently running operating system.
old-location: display\videoportgetversion.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortGetVersion function"]
ms.keywords: VideoPortGetVersion, VideoPortGetVersion function [Display Devices], VideoPort_Functions_b616e0f2-430a-43ca-a43f-44cdcaec757f.xml, display.videoportgetversion, video/VideoPortGetVersion
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortGetVersion
 - video/VideoPortGetVersion
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortGetVersion
---

# VideoPortGetVersion function


## -description

The <b>VideoPortGetVersion</b> function gets version information about the currently running operating system.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the miniport driver's device extension.

### -param pVpOsVersionInfo 

[in, out]
Pointer to a <a href="/windows-hardware/drivers/ddi/video/ns-video-_vposversioninfo">VPOSVERSIONINFO</a> structure that will receive the operating system version information. The caller should set the <b>Size</b> member of the VPOSVERSIONINFO structure to the size, in bytes, of that structure.

## -returns

<b>VideoPortGetVersionInfo</b> returns NO_ERROR if it successfully obtained the operating system version information. If the <b>Size</b> member of the VPOSVERSIONINFO does not contains the correct size of this structure, the function returns ERROR_INVALID_PARAMETER

## -see-also

<a href="/windows-hardware/drivers/ddi/video/ns-video-_vposversioninfo">VPOSVERSIONINFO</a>
