---
UID: NC:ks.PFNKSINTERSECTHANDLER
title: PFNKSINTERSECTHANDLER
author: windows-driver-content
description: A streaming minidriver's KStrIntersectHandler routine is called to compare a data range to determine if there is an intersection, and if so, the data format of the intersection.
old-location: stream\kstrintersecthandler.htm
old-project: stream
ms.assetid: ec4ca8b0-5386-4a03-8cf8-46852c168732
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KStrIntersectHandler, KStrIntersectHandler routine [Streaming Media Devices], PFNKSINTERSECTHANDLER, ks/KStrIntersectHandler, ksfunc_25fa087e-9d66-4479-aa4c-632a63ee6779.xml, stream.kstrintersecthandler
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
-	KStrIntersectHandler
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSINTERSECTHANDLER callback


## -description


A streaming minidriver's <i>KStrIntersectHandler</i> routine is called to compare a data range to determine if there is an intersection, and if so, the data format of the intersection.


## -prototype


````
PFNKSINTERSECTHANDLER KStrIntersectHandler;

NTSTATUS KStrIntersectHandler(
  _In_      PIRP         Irp,
  _In_      PKSP_PIN     Pin,
  _In_      PKSDATARANGE DataRange,
  _Out_opt_ PVOID        Data
)
{ ... }
````


## -parameters




### -param Irp [in]

Specifies the IRP that handles the property request.


### -param Pin [in]

Specifies the specific property being queried and the pin factory identifier that was validated.


### -param DataRange [in]

Specifies the current data range to compare. The data range has been validated as either matching a particular range on the pin or as a wildcard match.


### -param Data [out, optional]

Specifies the data format returned, or the size, in bytes, of the data format.


## -returns



Returns STATUS_SUCCESS if there is a data intersection that fits in the supplied buffer. Otherwise, one of the following values is returned. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
For successful size queries. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
If the supplied buffer is too small.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MATCH</b></dt>
</dl>
</td>
<td width="60%">
If there is no intersection.

</td>
</tr>
</table>
 




## -see-also

<a href="..\ks\nf-ks-kspindataintersection.md">KsPinDataIntersection</a>



 

 


