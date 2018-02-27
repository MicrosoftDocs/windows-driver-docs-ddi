---
UID: NF:ntddk.RtlExtendCorrelationVector
title: RtlExtendCorrelationVector function
author: windows-driver-content
description: This routine extends the supplied correlation vector. For a correlation vector of the form X.i, the extended value is X.i.0.
old-location: kernel\rtlextendcorrelationvector.htm
old-project: kernel
ms.assetid: 26de5890-edef-4e38-834a-9823327a74c2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlExtendCorrelationVector, RtlExtendCorrelationVector function [Kernel-Mode Driver Architecture], kernel.rtlextendcorrelationvector, ntddk/RtlExtendCorrelationVector
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode)
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlExtendCorrelationVector
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlExtendCorrelationVector function


## -description



			
            This routine extends the supplied correlation vector. For
    a correlation vector of the form X.i, the extended value is
    X.i.0.


## -syntax


````
 NTSTATUS  RtlExtendCorrelationVector(
  _Inout_ PCORRELATION_VECTOR CorrelationVector
);
````


## -parameters




### -param CorrelationVector [in, out]

A pointer to a  <a href="..\ntddk\ns-ntddk-correlation_vector.md">CORRELATION_VECTOR</a> structure that represents the correlation vector to be extended.


## -returns




Returns an NTSTATUS value that indicates the success of failure of the operation. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The correlation vector was successfully incremented.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Extending the correlation vector resulted in
    a buffer overflow because as the extended value is no longer a valid
    correlation vector.

</td>
</tr>
</table>
 



