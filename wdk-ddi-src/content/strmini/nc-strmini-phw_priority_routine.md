---
UID: NC:strmini.PHW_PRIORITY_ROUTINE
title: PHW_PRIORITY_ROUTINE
author: windows-driver-content
description: StrMiniPriorityRoutine is a minidriver-supplied callback routine to be executed at a specified priority level.
old-location: stream\strminipriorityroutine.htm
old-project: stream
ms.assetid: 775ab6aa-eda7-4774-8fe8-8b1838b3972f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.strminipriorityroutine, StrMiniPriorityRoutine routine [Streaming Media Devices], StrMiniPriorityRoutine, PHW_PRIORITY_ROUTINE, PHW_PRIORITY_ROUTINE, strmini/StrMiniPriorityRoutine, strmini-routines_718339c9-e072-4d3e-a9ec-a0ce2cce4f90.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: strmini.h
req.include-header: Strmini.h
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
-	strmini.h
apiname:
-	StrMiniPriorityRoutine
product: Windows
targetos: Windows
req.typenames: ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
req.product: Windows 10 or later.
---

# PHW_PRIORITY_ROUTINE callback


## -description


<i>StrMiniPriorityRoutine</i> is a minidriver-supplied callback routine to be executed at a specified priority level.


## -prototype


````
PHW_PRIORITY_ROUTINE StrMiniPriorityRoutine;

VOID StrMiniPriorityRoutine(
  _In_ PVOID Context
)
{ ... }
````


## -parameters




### -param Context [in]

Pointer to a minidriver-allocated buffer. The minidriver provides a pointer to this buffer in the Context parameter of its call to <a href="..\strmini\nf-strmini-streamclasscallatnewpriority.md">StreamClassCallAtNewPriority</a>.


## -returns



None




## -remarks



The minidriver provides a pointer to this routine in the <b>Priority</b> parameter of a call to <a href="..\strmini\nf-strmini-streamclasscallatnewpriority.md">StreamClassCallAtNewPriority</a>.




## -see-also

<a href="..\strmini\nf-strmini-streamclasscallatnewpriority.md">StreamClassCallAtNewPriority</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20StrMiniPriorityRoutine routine%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

