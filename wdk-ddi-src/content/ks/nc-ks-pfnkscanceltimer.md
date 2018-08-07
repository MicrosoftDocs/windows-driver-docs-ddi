---
UID: NC:ks.PFNKSCANCELTIMER
title: PFNKSCANCELTIMER
author: windows-driver-content
description: A streaming minidriver's KStrCancelTimer routine is called to cancel a custom timer object that was previously specified in the SetTimer parameter in a call to KsAllocateDefaultClockEx.
old-location: stream\kstrcanceltimer.htm
tech.root: stream
ms.assetid: bdfe0fc3-1b25-493f-9d70-3b6d680fde50
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KStrCancelTimer, KStrCancelTimer routine [Streaming Media Devices], PFNKSCANCELTIMER, ks/KStrCancelTimer, ksfunc_10ed86a1-d424-45d1-a420-3e4ce3a95a05.xml, stream.kstrcanceltimer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	KStrCancelTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSCANCELTIMER callback function


## -description


A streaming minidriver's <i>KStrCancelTimer</i> routine is called to cancel a custom timer object that was previously specified in the <i>SetTimer</i> parameter in a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff560955">KsAllocateDefaultClockEx</a>.


## -parameters




### -param Context [in]

Pointer to the minidriver-supplied information context. The minidriver passes the information context to <a href="https://msdn.microsoft.com/library/windows/hardware/ff560955">KsAllocateDefaultClockEx</a> in the function's <i>DeferredContext</i> parameter when the minidriver allocates a custom DPC timer object.


### -param Timer [in]

Pointer to the minidriver's custom timer object to cancel.


## -returns



Returns <b>TRUE</b> if the specified timer object is in the system timer queue, or <b>FALSE</b> otherwise.




## -remarks



Minidrivers can optionally supply a <i>KStrCancelTimer</i> callback function as a parameter to <b>KsAllocateDefaultClockEx</b>.

The minidriver-supplied <i>KStrCancelTimer</i> must have the same characteristics as <a href="https://msdn.microsoft.com/library/windows/hardware/ff551970">KeCancelTimer</a>.

If a minidriver supplies a <i>KStrCancelTimer</i> callback function, the minidriver must also supply a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567203">KStrSetTimer</a> callback function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567203">KStrSetTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551970">KeCancelTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560955">KsAllocateDefaultClockEx</a>
 

 

