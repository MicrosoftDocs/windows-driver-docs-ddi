---
UID: NF:video.VideoPortInterlockedIncrement
title: VideoPortInterlockedIncrement function
description: The VideoPortInterlockedIncrement function increments a caller-supplied variable as an atomic operation.
old-location: display\videoportinterlockedincrement.htm
tech.root: display
ms.assetid: d3507214-82bc-4d73-8562-2843d7876137
ms.date: 05/10/2018
ms.keywords: VideoPortInterlockedIncrement, VideoPortInterlockedIncrement function [Display Devices], VideoPort_Functions_ae59ee02-e3b2-43f6-8b93-8fe6bcedf248.xml, display.videoportinterlockedincrement, video/VideoPortInterlockedIncrement
ms.topic: function
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortInterlockedIncrement
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortInterlockedIncrement function


## -description


The <b>VideoPortInterlockedIncrement</b> function increments a caller-supplied variable as an atomic operation.


## -parameters




### -param Addend [in]

Pointer to the variable to be incremented.


## -returns



<b>VideoPortInterlockedIncrement</b> returns the incremented value.




## -remarks



When possible and whenever appropriate, <b>VideoPortInterlockedIncrement</b> is implemented inline by the compiler. It can be safely used on pageable data.

This function is atomic only with respect to other <b>VideoPortInterlocked</b><i>Xxx</i> calls. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570322">VideoPortInterlockedDecrement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570323">VideoPortInterlockedExchange</a>
 

 

