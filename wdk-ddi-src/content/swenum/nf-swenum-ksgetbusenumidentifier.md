---
UID: NF:swenum.KsGetBusEnumIdentifier
title: KsGetBusEnumIdentifier function
author: windows-driver-content
description: The KsGetBusEnumIdentifier function retrieves the software bus enumerator identifier for the bus device associated with the given IRP.
old-location: stream\ksgetbusenumidentifier.htm
old-project: stream
ms.assetid: 50e14e01-5879-4a84-a8c2-f03c953dbeec
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , B, E, G, I, K, KsGetBusEnumIdentifier, KsGetBusEnumIdentifier function [Streaming Media Devices], d, e, f, i, ksfunc_c001aace-8c97-48cb-ae8b-9e7075d51960.xml, m, n, r, s, stream.ksgetbusenumidentifier, swenum/KsGetBusEnumIdentifier, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: swenum.h
req.include-header: Swenum.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsGetBusEnumIdentifier
product: Windows
targetos: Windows
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# KsGetBusEnumIdentifier function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsGetBusEnumIdentifier</b> function retrieves the software bus enumerator identifier for the bus device associated with the given IRP. 


## -syntax


````
NTSTATUS KsGetBusEnumIdentifier(
  _Inout_ PIRP Irp
);
````


## -parameters




### -param Irp [in, out]

Pointer to the IRP that specifies the address and size of the user output buffer to receive the requested bus enumerator identifier.


## -returns



Returns STATUS_SUCCESS if the bus enumerator identifier was retrieved successfully. Otherwise, it returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified device is not valid

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The specified buffer was not large enough

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
No buffer was specified (the required buffer size is returned in the Irp).

</td>
</tr>
</table>
 



