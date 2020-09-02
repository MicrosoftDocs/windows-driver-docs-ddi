---
UID: NF:ntifs.SecMakeSPN
title: SecMakeSPN function (ntifs.h)
description: SecMakeSPN creates a service provider name string that can be used when communicating with specific security service providers.
old-location: ifsk\secmakespn.htm
tech.root: ifsk
ms.assetid: e294832a-f0f2-49ab-b215-7c0e67e5ec13
ms.date: 04/16/2018
keywords: ["SecMakeSPN function"]
ms.keywords: SecMakeSPN, SecMakeSPN function [Installable File System Drivers], ifsk.secmakespn, ksecddref_0225b4c1-8cfd-49cc-a69a-85da507c401e.xml, ntifs/SecMakeSPN
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
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
req.lib: Ksecdd.lib
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SecMakeSPN
 - ntifs/SecMakeSPN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ksecdd.lib
 - Ksecdd.dll
api_name:
 - SecMakeSPN
---

# SecMakeSPN function


## -description

<b>SecMakeSPN</b> creates a service provider name string that can be used when communicating with specific security service providers.

## -parameters

### -param ServiceClass 

[in]
A pointer to a Unicode string specifying the service class for the security service provider.

### -param ServiceName 

[in]
A pointer to a Unicode string specifying the service name for the security service provider.

### -param OPTIONAL

<p>A pointer to an optional Unicode string specifying the instance name for connecting with the security service provider. </p>

### -param Spn 

[in, out]
A pointer to a Unicode string for storing the security service provider name string created by this function.

### -param Allocate 

[in]
A Boolean variable indicating if the memory for storing the <i>Spn</i> Unicode string should be allocated by this function. If this parameter is true, memory for <i>Spn</i> will be allocated from paged pool.

## -returns

<b>SecMakeSPN</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

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
The <i>Allocate</i> parameter was set to false and one of the following conditions occurred:

The <i>Spn </i>parameter was a null pointer.

The maximum length for the <i>Spn</i> Unicode string parameter was too small.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A total length of the <i>Spn</i> parameter exceeds 65535 bytes.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
The <i>Allocate</i> parameter was set to true, but the memory allocation request failed.

</td>
</tr>
</table>

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556585">SecMakeSPNEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556592">SecMakeSPNEx2</a>

