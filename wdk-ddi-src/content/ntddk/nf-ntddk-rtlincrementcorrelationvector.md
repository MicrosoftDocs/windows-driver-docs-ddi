---
UID: NF:ntddk.RtlIncrementCorrelationVector
title: RtlIncrementCorrelationVector function
author: windows-driver-content
description: Increments the specified correlation vector. For a correlation vector of the form X.i, the incremented value is be X.(i+1).
old-location: kernel\rtlincrementcorrelationvector.htm
tech.root: kernel
ms.assetid: bb252dd5-9bf3-41bd-ab46-9524735970c5
ms.date: 04/30/2018
ms.keywords: RtlIncrementCorrelationVector, RtlIncrementCorrelationVector function [Kernel-Mode Driver Architecture], kernel.rtlincrementcorrelationvector, ntddk/RtlIncrementCorrelationVector
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlIncrementCorrelationVector
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIncrementCorrelationVector function


## -description


Increments the specified [correlation vector](https://github.com/Microsoft/CorrelationVector). For
    a correlation vector of the form X.i, the incremented value is be
    X.(i+1).


## -parameters




### -param CorrelationVector [in, out]

A pointer to a  <a href="https://msdn.microsoft.com/35c1799f-2012-42b0-95e6-6902c818a094">CORRELATION_VECTOR</a> structure that represents the correlation vector to be incremented.


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
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
Incrementing the correlation vector resulted in
    a buffer overflow because as the incremented value is no longer a valid
    correlation vector.

</td>
</tr>
</table>
 



