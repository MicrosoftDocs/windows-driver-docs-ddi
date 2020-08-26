---
UID: NF:ntddk.RtlExtendCorrelationVector
title: RtlExtendCorrelationVector function (ntddk.h)
description: This routine extends the supplied correlation vector. For a correlation vector of the form X.i, the extended value is X.i.0.
old-location: kernel\rtlextendcorrelationvector.htm
tech.root: kernel
ms.assetid: 26de5890-edef-4e38-834a-9823327a74c2
ms.date: 04/30/2018
keywords: ["RtlExtendCorrelationVector function"]
ms.keywords: RtlExtendCorrelationVector, RtlExtendCorrelationVector function [Kernel-Mode Driver Architecture], kernel.rtlextendcorrelationvector, ntddk/RtlExtendCorrelationVector
f1_keywords:
 - "ntddk/RtlExtendCorrelationVector"
 - "RtlExtendCorrelationVector"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlExtendCorrelationVector
targetos: Windows
req.typenames: 
---

# RtlExtendCorrelationVector function


## -description



			
            This routine extends the supplied [correlation vector](https://github.com/Microsoft/CorrelationVector). For
    a correlation vector of the form X.i, the extended value is
    X.i.0.


## -parameters




### -param CorrelationVector 
[in, out]
A pointer to a  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-correlation_vector">CORRELATION_VECTOR</a> structure that represents the correlation vector to be extended.


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
 



