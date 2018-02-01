---
UID: NF:ntddk.PsGetJobServerSilo
title: PsGetJobServerSilo function
author: windows-driver-content
description: This routine returns the effective ServerSilo for the job. The returned pointer is valid as long as the supplied Job object remains referenced.
old-location: kernel\psgetjobserversilo.htm
old-project: kernel
ms.assetid: 8EBCBC06-8373-43EA-91F5-6C8A439C0EAD
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.psgetjobserversilo, PsGetJobServerSilo, PsGetJobServerSilo routine [Kernel-Mode Driver Architecture], ntddk/PsGetJobServerSilo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PsGetJobServerSilo
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsGetJobServerSilo function


## -description


This routine returns the effective <i>ServerSilo</i> for the job. The returned pointer is valid as long as the supplied <i>Job</i> object remains referenced.


<div class="alert"><b>Note</b>  This returns a <i>ServerSilo</i> or a value indicating the host silo. Unlike <a href="..\ntddk\nf-ntddk-psgetjobsilo.md">PsGetJobSilo</a>, it will not return an app silo, even if one is present.</div>
<div> </div>



## -syntax


````
NTSTATUS PsGetJobServerSilo(
  _In_opt_ PEJOB  Job,
  _Out_    PESILO *ServerSilo
);
````


## -parameters




### -param Job [in, optional]

A job object.


### -param ServerSilo [out]

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


