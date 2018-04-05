---
UID: NS:d3dkmthk._D3DKMT_PRESENT_STATS
title: "_D3DKMT_PRESENT_STATS"
author: windows-driver-content
description: The D3DKMT_PRESENT_STATS structure describes present status for a rendering device.
old-location: display\d3dkmt_present_stats.htm
old-project: display
ms.assetid: fd292f3c-2cf7-4f17-999b-a82b2a3a8e0e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_PRESENT_STATS, D3DKMT_PRESENT_STATS structure [Display Devices], OpenGL_Structs_181828f7-c22f-4f23-914d-83a8961cdefe.xml, _D3DKMT_PRESENT_STATS, d3dkmthk/D3DKMT_PRESENT_STATS, display.d3dkmt_present_stats
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dkmthk.h
api_name:
-	D3DKMT_PRESENT_STATS
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_PRESENT_STATS
---

# _D3DKMT_PRESENT_STATS structure


## -description


The D3DKMT_PRESENT_STATS structure describes present status for a rendering device.


## -struct-fields




### -field PresentCount

[out] A UINT value that indicates the number of times that the OpenGL installable client driver (ICD) called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547091">D3DKMTPresent</a> function on a rendering device or swap chain. After the maximum value is reached, <b>PresentCount</b> starts over at zero. When a new rendering device is created, <b>PresentCount</b> is initialized to zero. The operating system maintains a present counter for each swap chain that is created.


### -field PresentRefreshCount

[out] A UINT value that indicates the number of times the display controller outputs a new video frame, which occurs at the beginning of each vertical retrace period. The operating system maintains a present refresh counter for each video display controller output in the operating system. <b>PresentRefreshCount</b> is initialized to an unspecified value. 


### -field SyncRefreshCount

[out] A UINT value that indicates the number of the most recent capture of the timing information in the <b>SyncQPCTime</b> and <b>SyncGPUTime</b> members.


### -field SyncQPCTime

[out] The computer processing unit (CPU) time that the current video frame was output at (that is, the CPU time that the vertical retrace started).


### -field SyncGPUTime

[out] The graphics processing unit (GPU) time that the current video frame was output at (that is, the GPU time that the vertical retrace started).


## -remarks



When a present operation is retired, the operating system maintains a correspondence (mapping) between the value in <b>PresentCount</b> and the value in <b>PresentRefreshCount</b>; that is, when the operating system finishes a present operation as a scanned out video frame, the value in <b>PresentRefreshCount</b> that the present operation was finished with is associated with the value in <b>PresentCount</b> of the retired present operation. 

The operating system maintains timing information within a rendering device and associates the timing information with a display output. When the GPU can maintain the GPU time (<b>SyncGPUTime</b>), the GPU time operates at a device-specific frequency. To let applications relate GPU time to other operations in the system, the operating system maintains a correspondence between GPU time and CPU time (<b>SyncQPCTime</b>). When the GPU cannot maintain such GPU time, the operating system maintains only CPU time and the associated GPU time is always zero. 

Present statistics cannot work for windowed-mode devices. For windowed mode, each structure member is set to zero.

<div class="alert"><b>Note</b>    The operating system might not update the <b>SyncRefreshCount</b>, <b>SyncQPCTime</b>, and <b>SyncGPUTime</b> members on every frame.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547091">D3DKMTPresent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547905">D3DKMT_DEVICEPRESENT_STATE</a>
 

 

