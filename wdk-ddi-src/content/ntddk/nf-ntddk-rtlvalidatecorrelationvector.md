---
UID: NF:ntddk.RtlValidateCorrelationVector
title: RtlValidateCorrelationVector function (ntddk.h)
description: Validates the specified correlation vector to check whether it conforms to the Correlation Vector Specification (v2).
old-location: kernel\rtlvalidatecorrelationvector.htm
tech.root: kernel
ms.assetid: a73ab33b-3e8c-43d8-8547-1483bcd2af52
ms.date: 04/30/2018
keywords: ["RtlValidateCorrelationVector function"]
ms.keywords: RtlValidateCorrelationVector, RtlValidateCorrelationVector function [Kernel-Mode Driver Architecture], kernel.rtlvalidatecorrelationvector, ntddk/RtlValidateCorrelationVector
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlValidateCorrelationVector
 - ntddk/RtlValidateCorrelationVector
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlValidateCorrelationVector
---

# RtlValidateCorrelationVector function


## -description

Validates the specified [correlation vector](https://github.com/Microsoft/CorrelationVector) to check whether it conforms to the Correlation Vector Specification (v2).
    The function specifically checks if the first 22 bytes are a valid base64 representation of a 16 byte
        buffer
         and the remaining characters match the (\.\d+)+  regular expression.

## -parameters

### -param Vector

<p>A pointer to a  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-correlation_vector"><b>CORRELATION_VECTOR</b></a> structure that represents the correlation vector to be validated.</p>

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
The correlation vector is valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The supplied correlation vector is invalid.

</td>
</tr>
</table>

