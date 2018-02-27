---
UID: NF:video.VideoPortCreateSpinLock
title: VideoPortCreateSpinLock function
author: windows-driver-content
description: The VideoPortCreateSpinLock function creates a spin lock.
old-location: display\videoportcreatespinlock.htm
old-project: display
ms.assetid: bb5f3b3e-3358-4181-9c4d-1871be1a7b7b
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortCreateSpinLock function


## -description


The <b>VideoPortCreateSpinLock</b> function creates a spin lock.


## -syntax


````
VP_STATUS VideoPortCreateSpinLock(
  _In_  PVOID      HwDeviceExtension,
  _Out_ PSPIN_LOCK *SpinLock
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param SpinLock [out]

Pointer to a memory location that will receive a pointer to the newly created spin lock.


## -returns



On success the function returns NO_ERROR. If an error occurs, the function returns an appropriate error code.




## -remarks



This routine must be called before an initial call to <a href="..\video\nf-video-videoportacquirespinlock.md">VideoPortAcquireSpinLock</a> or to any other support routine that requires a spin lock as an argument. 




## -see-also

<a href="..\video\nf-video-videoportdeletespinlock.md">VideoPortDeleteSpinLock</a>



<a href="..\video\nf-video-videoportacquirespinlock.md">VideoPortAcquireSpinLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortCreateSpinLock function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

