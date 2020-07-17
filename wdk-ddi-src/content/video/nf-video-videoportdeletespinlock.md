---
UID: NF:video.VideoPortDeleteSpinLock
title: VideoPortDeleteSpinLock function (video.h)
description: The VideoPortDeleteSpinLock function deletes a given spin lock.
old-location: display\videoportdeletespinlock.htm
tech.root: display
ms.assetid: 74845e4d-0fa1-4625-96a7-2fddec8b901d
ms.date: 05/10/2018
keywords: ["VideoPortDeleteSpinLock function"]
ms.keywords: VideoPortDeleteSpinLock, VideoPortDeleteSpinLock function [Display Devices], VideoPort_Functions_d98d74d6-bf9c-441b-95e3-a3455927dd45.xml, display.videoportdeletespinlock, video/VideoPortDeleteSpinLock
f1_keywords:
 - "video/VideoPortDeleteSpinLock"
 - "VideoPortDeleteSpinLock"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortDeleteSpinLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortDeleteSpinLock function


## -description


The <b>VideoPortDeleteSpinLock</b> function deletes a given spin lock.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param SpinLock [in]

Pointer to the spin lock to delete.


## -returns



If the spin lock is successfully deleted, <b>VideoPortDeleteSpinLock</b> returns NO_ERROR.




## -remarks



A miniport driver uses this function to delete a spin lock that was previously created in a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportcreatespinlock">VideoPortCreateSpinLock</a>.

This routine cannot be called from an ISR or from a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportsynchronizeexecution">VideoPortSynchronizeExecution</a> callback requested where the <i>Priority</i> parameter is set to either <b>VpMediumPriority</b> or <b>VpHighPriority</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportcreatespinlock">VideoPortCreateSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportsynchronizeexecution">VideoPortSynchronizeExecution</a>
 

 

