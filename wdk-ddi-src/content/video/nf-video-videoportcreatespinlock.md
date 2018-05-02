---
UID: NF:video.VideoPortCreateSpinLock
title: VideoPortCreateSpinLock function
author: windows-driver-content
description: The VideoPortCreateSpinLock function creates a spin lock.
old-location: display\videoportcreatespinlock.htm
old-project: display
ms.assetid: bb5f3b3e-3358-4181-9c4d-1871be1a7b7b
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: VideoPortCreateSpinLock, VideoPortCreateSpinLock function [Display Devices], VideoPort_Functions_64ab2562-155d-4cec-8612-42aca51d909b.xml, display.videoportcreatespinlock, video/VideoPortCreateSpinLock
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortCreateSpinLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortCreateSpinLock function


## -description


The <b>VideoPortCreateSpinLock</b> function creates a spin lock.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param SpinLock [out]

Pointer to a memory location that will receive a pointer to the newly created spin lock.


## -returns



On success the function returns NO_ERROR. If an error occurs, the function returns an appropriate error code.




## -remarks



This routine must be called before an initial call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570175">VideoPortAcquireSpinLock</a> or to any other support routine that requires a spin lock as an argument. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570175">VideoPortAcquireSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570293">VideoPortDeleteSpinLock</a>
 

 

