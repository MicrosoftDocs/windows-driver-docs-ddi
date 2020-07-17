---
UID: NF:video.VideoPortWritePortUchar
title: VideoPortWritePortUchar function (video.h)
description: The VideoPortWritePortUchar function writes a byte to a mapped I/O port.
old-location: display\videoportwriteportuchar.htm
tech.root: display
ms.assetid: 0f05f765-ca59-4a92-91a0-f1123dd9cd6f
ms.date: 05/10/2018
keywords: ["VideoPortWritePortUchar function"]
ms.keywords: VideoPortWritePortUchar, VideoPortWritePortUchar function [Display Devices], VideoPort_Functions_cfd3f257-e96f-4f75-a335-6b78aaa47c70.xml, display.videoportwriteportuchar, video/VideoPortWritePortUchar
f1_keywords:
 - "video/VideoPortWritePortUchar"
 - "VideoPortWritePortUchar"
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
req.irql: Any level (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortWritePortUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortWritePortUchar function


## -description


The <b>VideoPortWritePortUchar</b> function writes a byte to a mapped I/O port.


## -parameters




### -param Port

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


### -param Value

Specifies a byte to be transferred to the adapter.


## -returns



None




## -remarks



A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWritePortUchar</b>.

Callers of <b>VideoPortWritePortUchar</b> can be running at any IRQL, provided that the memory pointed to by the <i>Port</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
 

 

