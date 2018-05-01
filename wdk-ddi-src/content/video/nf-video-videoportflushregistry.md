---
UID: NF:video.VideoPortFlushRegistry
title: VideoPortFlushRegistry function
author: windows-driver-content
description: The VideoPortFlushRegistry function flushes registry keys and values associated with the video miniport driver.
old-location: display\videoportflushregistry.htm
old-project: display
ms.assetid: 8b940eec-dac6-4a01-afc8-73115bf994c3
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: VideoPortFlushRegistry, VideoPortFlushRegistry function [Display Devices], VideoPort_Functions_fe7df781-6130-484d-b582-55446711fef6.xml, display.videoportflushregistry, video/VideoPortFlushRegistry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortFlushRegistry
product: Windows
targetos: Windows
req.typenames: 
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570316">VideoPortGetRegistryParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570365">VideoPortSetRegistryParameters</a>
 

 

