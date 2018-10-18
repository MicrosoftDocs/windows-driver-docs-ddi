---
UID: NF:ks.KsPinDataIntersectionEx
title: KsPinDataIntersectionEx function
author: windows-driver-content
description: The KsPinDataIntersectionEx function handles the KSPROPERTY_PIN_DATAINTERSECTION through a callback function.
old-location: stream\kspindataintersectionex.htm
tech.root: stream
ms.assetid: 4d471d91-7b2c-441d-a640-4f66ef7f1b2f
ms.date: 4/23/2018
ms.keywords: KsPinDataIntersectionEx, KsPinDataIntersectionEx function [Streaming Media Devices], ks/KsPinDataIntersectionEx, ksfunc_22cbace6-b96b-44d7-9c30-24580f37dd58.xml, stream.kspindataintersectionex
ms.topic: function
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
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsPinDataIntersectionEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinDataIntersectionEx function


## -description


The <b>KsPinDataIntersectionEx</b> function handles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565198">KSPROPERTY_PIN_DATAINTERSECTION</a> through a callback function.


## -parameters




### -param Irp [in]

Specifies the IRP that describes the property request.


### -param Pin [in]

Specifies the specific property that is being queried.


### -param Data [out]

Specifies the pin property-specific data.


### -param DescriptorsCount [in]

Specifies the number of descriptor structures.


### -param Descriptor [in]

Specifies the pointer to the list of pin information structures.


### -param DescriptorSize [in]

Size of the descriptor structures, in bytes.


### -param IntersectHandler [in, optional]

Contains the optional minidriver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff567185">KStrIntersectHandlerEx</a> callback function to compare data ranges.


### -param HandlerContext [in, optional]

Optional context that is supplied to the handler.


## -returns



Returns STATUS_SUCCESS; otherwise, an error specific to the property that is being handled.




## -remarks



<b>KsPinDataIntersectionEx</b> is very similar to <b>KsPinDataIntersection</b>, except for some of the following slight differences:

<ul>
<li>
In <b>KsPinDataIntersectionEx</b>, the size of the descriptor is passed, a feature that allows extended descriptors.

</li>
<li>
The data intersection callback function is prototyped differently in the extended version (NTSTATUS Callback (<i>Context</i>, <i>Irp</i>, <i>Pin</i>, <i>DataRange</i>, <i>MatchingDataRange</i>, <i>DataBufferSize</i>, <i>Data</i>, <i>DataSize</i>)) versus <b>KsPinDataIntersection</b> (NTSTATUS Callback (<i>Irp</i>, <i>Pin</i>, <i>DataRange</i>, <i>Data</i>)).

</li>
<li>
The output buffer (<i>Data</i>) length is passed as a parameter to the data intersection callback function (<i>DataBufferSize</i>) rather than being extracted from the current I/O stack location.

</li>
<li>
The data intersection callback function is passed a <i>Context</i> parameter (the same <i>Context</i> parameter passed to <b>KsPinDataIntersectionEx</b>).

</li>
<li>
The size of the resultant format is passed back in <i>DataSize</i> instead of <i>Irp</i>-&gt;IoStatus.Information.

</li>
</ul>
These differences excepted, <b>KsPinDataIntersection</b> and <b>KsPinDataIntersectionEx</b> operate similarly.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567185">KStrIntersectHandlerEx</a>
 

 

