---
UID: NF:video.VideoPortFreePool
title: VideoPortFreePool function
author: windows-driver-content
description: The VideoPortFreePool function deallocates a block of pool memory previously allocated by VideoPortAllocatePool.
old-location: display\videoportfreepool.htm
tech.root: display
ms.assetid: 84e4f178-87d3-4f40-b4fc-7959818305fd
ms.date: 5/10/2018
ms.keywords: VideoPortFreePool, VideoPortFreePool function [Display Devices], VideoPort_Functions_a2b1e2c4-9f8d-455b-8484-c51e0669d526.xml, display.videoportfreepool, video/VideoPortFreePool
ms.topic: function
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortFreePool
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortFreePool function


## -description


The <b>VideoPortFreePool</b> function deallocates a block of pool memory previously allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570180">VideoPortAllocatePool</a>.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param Ptr [in]

Pointer to the first byte of the memory to be freed.


## -returns



None




## -remarks



<b>VideoPortFreePool</b> is intended to replace <b>VideoPortReleaseBuffer</b>, which is obsolete.

Callers of <b>VideoPortFreePool</b> must be running at IRQL &lt;= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must have specified a <b>VpNonPaged </b><i>XxxPoolType</i> when the memory was allocated. Otherwise, the caller must be running at IRQL &lt; DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570178">VideoPortAllocateCommonBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570180">VideoPortAllocatePool</a>
 

 

