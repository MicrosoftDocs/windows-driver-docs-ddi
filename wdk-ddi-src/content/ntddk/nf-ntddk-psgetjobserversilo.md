---
UID: NF:ntddk.PsGetJobServerSilo
title: PsGetJobServerSilo function (ntddk.h)
description: This routine returns the effective ServerSilo for the job. The returned pointer is valid as long as the supplied Job object remains referenced.
old-location: kernel\psgetjobserversilo.htm
tech.root: kernel
ms.assetid: 8EBCBC06-8373-43EA-91F5-6C8A439C0EAD
ms.date: 04/30/2018
keywords: ["PsGetJobServerSilo function"]
ms.keywords: PsGetJobServerSilo, PsGetJobServerSilo routine [Kernel-Mode Driver Architecture], kernel.psgetjobserversilo, ntddk/PsGetJobServerSilo
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PsGetJobServerSilo
 - ntddk/PsGetJobServerSilo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsGetJobServerSilo
---

# PsGetJobServerSilo function


## -description

This routine returns the effective <i>ServerSilo</i> for the job. The returned pointer is valid as long as the supplied <i>Job</i> object remains referenced.


<div class="alert"><b>Note</b>  This returns a <i>ServerSilo</i> or a value indicating the host silo. Unlike <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetjobsilo">PsGetJobSilo</a>, it will not return an app silo, even if one is present.</div>
<div> </div>

## -parameters

### -param Job 

[in, optional]
A job object.

### -param ServerSilo 

[out]
 A pointer that receives the server silo for the job.

## -returns

The following NT status codes are returned.

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
The <i>Job</i> parameter is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
A PESILO is returned successfully.

</td>
</tr>
</table>

## -remarks

<b>STATUS_SUCCESS</b> is returned even if a server silo is not in effect for the job. In that case, it will return the default host silo.

