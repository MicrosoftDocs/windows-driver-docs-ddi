---
UID: NF:ntddk.RtlInitializeCorrelationVector
title: RtlInitializeCorrelationVector function (ntddk.h)
description: Initializes the specified correlation vector with the supplied GUID.
old-location: kernel\rtlinitializecorrelationvector.htm
tech.root: kernel
ms.assetid: ebf5ccbe-3325-4d3d-86c9-230776f2c9ef
ms.date: 04/30/2018
ms.keywords: RtlInitializeCorrelationVector, RtlInitializeCorrelationVector function [Kernel-Mode Driver Architecture], kernel.rtlinitializecorrelationvector, ntddk/RtlInitializeCorrelationVector
f1_keywords:
 - "ntddk/RtlInitializeCorrelationVector"
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
- RtlInitializeCorrelationVector
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlInitializeCorrelationVector function


## -description



			
              Initializes the specified [correlation vector](https://github.com/Microsoft/CorrelationVector) with
    the supplied GUID.


## -parameters




### -param CorrelationVector [in, out]

A pointer to a  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-correlation_vector">CORRELATION_VECTOR</a> structure that represents the correlation vector to be initialized.


### -param Version [in]

The version of the correlation vector. Possible values are: 

<ul>
<li>RTL_CORRELATION_VECTOR_VERSION_1</li>
<li>RTL_CORRELATION_VECTOR_VERSION_2</li>
<li>RTL_CORRELATION_VECTOR_VERSION_CURRENT</li>
</ul>

### -param Guid [in]

The GUID to initialize the correlation vector. The first 22 bytes
            of the correlation vector are a base64 representation of the GUID. This value must not be NULL.


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
The correlation vector was successfully initialized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The supplied GUID is null.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-correlation_vector">CORRELATION_VECTOR</a>
 

 

