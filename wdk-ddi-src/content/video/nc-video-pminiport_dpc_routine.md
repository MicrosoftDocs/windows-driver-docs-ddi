---
UID: NC:video.PMINIPORT_DPC_ROUTINE
title: PMINIPORT_DPC_ROUTINE
author: windows-driver-content
description: The HwVidDpcRoutine function is a miniport driver-implemented callback that is called when a queued DPC gets scheduled.
old-location: display\hwviddpcroutine.htm
old-project: display
ms.assetid: d4b443a2-3665-4e7c-b84a-5388a8fe8681
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.hwviddpcroutine, HwVidDpcRoutine callback function [Display Devices], HwVidDpcRoutine, PMINIPORT_DPC_ROUTINE, PMINIPORT_DPC_ROUTINE, video/HwVidDpcRoutine, VideoMiniport_Functions_5d605867-89d7-44a9-b08b-c49ffaa90244.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	video.h
apiname:
-	HwVidDpcRoutine
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PMINIPORT_DPC_ROUTINE callback


## -description


<i>The HwVidDpcRoutine</i> function is a miniport driver-implemented callback that is called when a queued DPC gets scheduled.


## -prototype


````
PMINIPORT_DPC_ROUTINE HwVidDpcRoutine;

VOID HwVidDpcRoutine(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID Context
)
{ ... }
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's hardware device extension. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param Context [in]

Contains any miniport driver-supplied data this function may need. <i>Context</i> can be <b>NULL</b> if the DPC implementation does not require additional information.


## -returns


None



## -remarks


The miniport driver queues this DPC by calling <a href="..\video\nf-video-videoportqueuedpc.md">VideoPortQueueDpc</a>.

Because <i>HwVidDpcRoutine </i>is called at DISPATCH_LEVEL, it must not manipulate any pageable code or data. Further, this function must be in nonpaged memory and should complete its operations as quickly as possible.



## -see-also

<a href="..\video\nf-video-videoportqueuedpc.md">VideoPortQueueDpc</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PMINIPORT_DPC_ROUTINE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

