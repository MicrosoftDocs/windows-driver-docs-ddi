---
UID: NC:strmini.PHW_PRIORITY_ROUTINE
title: PHW_PRIORITY_ROUTINE (strmini.h)
description: StrMiniPriorityRoutine is a minidriver-supplied callback routine to be executed at a specified priority level.
old-location: stream\strminipriorityroutine.htm
tech.root: stream
ms.assetid: 775ab6aa-eda7-4774-8fe8-8b1838b3972f
ms.date: 04/23/2018
ms.keywords: PHW_PRIORITY_ROUTINE, StrMiniPriorityRoutine, StrMiniPriorityRoutine routine [Streaming Media Devices], stream.strminipriorityroutine, strmini-routines_718339c9-e072-4d3e-a9ec-a0ce2cce4f90.xml, strmini/StrMiniPriorityRoutine
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- strmini.h
api_name:
- StrMiniPriorityRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# PHW_PRIORITY_ROUTINE callback function


## -description


<i>StrMiniPriorityRoutine</i> is a minidriver-supplied callback routine to be executed at a specified priority level.


## -parameters




### -param Context [in]

Pointer to a minidriver-allocated buffer. The minidriver provides a pointer to this buffer in the Context parameter of its call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclasscallatnewpriority">StreamClassCallAtNewPriority</a>.


## -returns



None




## -remarks



The minidriver provides a pointer to this routine in the <b>Priority</b> parameter of a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclasscallatnewpriority">StreamClassCallAtNewPriority</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclasscallatnewpriority">StreamClassCallAtNewPriority</a>
 

 

