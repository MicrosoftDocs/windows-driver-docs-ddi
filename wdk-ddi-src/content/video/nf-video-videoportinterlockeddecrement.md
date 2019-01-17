---
UID: NF:video.VideoPortInterlockedDecrement
title: VideoPortInterlockedDecrement function
description: The VideoPortInterlockedDecrement function decrements a caller-supplied variable as an atomic operation.
old-location: display\videoportinterlockeddecrement.htm
tech.root: display
ms.assetid: b72e3b7d-000b-4827-aa06-699a0bcc1840
ms.date: 05/10/2018
ms.keywords: VideoPortInterlockedDecrement, VideoPortInterlockedDecrement function [Display Devices], VideoPort_Functions_907ed72b-de68-432d-a9e4-b7c072628f9a.xml, display.videoportinterlockeddecrement, video/VideoPortInterlockedDecrement
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
-	VideoPortInterlockedDecrement
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortInterlockedDecrement function


## -description


The <b>VideoPortInterlockedDecrement</b> function decrements a caller-supplied variable as an atomic operation.


## -parameters




### -param Addend [in]

Pointer to the variable to be decremented.


## -returns



<b>VideoPortInterlockedDecrement</b> returns the decremented value.




## -remarks



When possible and whenever appropriate, <b>VideoPortInterlockedDecrement</b> is implemented inline by the compiler. It can be safely used on pageable data.

This function is atomic only with respect to other <b>VideoPortInterlocked</b><i>Xxx</i> calls. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570323">VideoPortInterlockedExchange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570324">VideoPortInterlockedIncrement</a>
 

 

