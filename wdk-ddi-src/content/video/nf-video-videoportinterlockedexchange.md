---
UID: NF:video.VideoPortInterlockedExchange
title: VideoPortInterlockedExchange function (video.h)
description: The VideoPortInterlockedExchange function locks or unlocks a block of memory by setting a user-defined lock variable to TRUE or FALSE, respectively. It returns the previously-held value of the lock variable.
old-location: display\videoportinterlockedexchange.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortInterlockedExchange function"]
ms.keywords: VideoPortInterlockedExchange, VideoPortInterlockedExchange function [Display Devices], VideoPort_Functions_2b2228a1-aca1-4661-ab6a-8747213bcd26.xml, display.videoportinterlockedexchange, video/VideoPortInterlockedExchange
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortInterlockedExchange
 - video/VideoPortInterlockedExchange
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortInterlockedExchange
---

# VideoPortInterlockedExchange function


## -description

The <b>VideoPortInterlockedExchange</b> function locks or unlocks a block of memory by setting a user-defined lock variable to <b>TRUE</b> or <b>FALSE</b>, respectively. It returns the previously-held value of the lock variable.

## -parameters

### -param Target 

[in, out]
Pointer to a user-defined lock variable that is used to control access to a memory buffer.

### -param Value 

[in]
Specifies the value to be stored in <i>Target</i>, which indicates whether the memory buffer is to be locked or unlocked. Use <b>TRUE</b> to lock the memory buffer, and <b>FALSE</b> to unlock the memory buffer.

## -returns

<b>VideoPortInterlockedExchange</b> returns the value that <i>Target</i> had prior to the function call.

## -remarks

<b>VideoPortInterlockedExchange</b> can be used to prevent DMA common-buffer contention in multiple-processor systems.

When the buffer is not being read from or written to, the lock variable should have a value of <b>FALSE</b>. A subsequent call to <b>VideoPortInterlockedExchange</b> with its <i>Target</i> parameter set to <b>TRUE</b> resets the lock variable to <b>TRUE</b>, after which this function returns <b>FALSE</b>. The buffer is now locked, preventing access by other threads. When the current operations on the buffer are complete, unlock the buffer with a call to <b>VideoPortInterlockedExchange</b> with its <i>Target</i> parameter set to <b>FALSE</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetcommonbuffer">VideoPortGetCommonBuffer</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportinterlockeddecrement">VideoPortInterlockedDecrement</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportinterlockedincrement">VideoPortInterlockedIncrement</a>
