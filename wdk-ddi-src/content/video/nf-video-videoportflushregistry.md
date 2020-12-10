---
UID: NF:video.VideoPortFlushRegistry
title: VideoPortFlushRegistry function (video.h)
description: The VideoPortFlushRegistry function flushes registry keys and values associated with the video miniport driver.
old-location: display\videoportflushregistry.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortFlushRegistry function"]
ms.keywords: VideoPortFlushRegistry, VideoPortFlushRegistry function [Display Devices], VideoPort_Functions_fe7df781-6130-484d-b582-55446711fef6.xml, display.videoportflushregistry, video/VideoPortFlushRegistry
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of the Windows operating systems.
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
 - VideoPortFlushRegistry
 - video/VideoPortFlushRegistry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortFlushRegistry
---

# VideoPortFlushRegistry function


## -description

The <b>VideoPortFlushRegistry</b> function flushes registry keys and values associated with the video miniport driver.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport driver's device extension.

## -returns

<b>VideoPortFlushRegistry</b> returns NO_ERROR.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetregistryparameters">VideoPortGetRegistryParameters</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportsetregistryparameters">VideoPortSetRegistryParameters</a>
