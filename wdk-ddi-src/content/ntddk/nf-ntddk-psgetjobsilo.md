---
UID: NF:ntddk.PsGetJobSilo
title: PsGetJobSilo function
author: windows-driver-content
description: This routine returns the first job in the hierarchy that is a Silo. The returned pointer is valid as long as the supplied Job object remains referenced.
old-location: kernel\psgetjobsilo.htm
old-project: kernel
ms.assetid: 1032282B-7CA3-4162-8FC2-1A4A683E9DEF
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: PsGetJobSilo, PsGetJobSilo routine [Kernel-Mode Driver Architecture], kernel.psgetjobsilo, ntddk/PsGetJobSilo
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PsGetJobSilo
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsGetJobSilo function


## -description


This routine returns the first job in the hierarchy that is a <i>Silo</i>.  The returned pointer is valid as long as the supplied <i>Job</i> object remains referenced.


<div class="alert"><b>Note</b>  This returns both app silos and server silos, whichever is first.</div>
<div> </div>



## -parameters




### -param Job [in]

A job object.


### -param Silo [out]

 A pointer that receives the silo for the job.


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
<dt><b>STATUS_JOB_NO_CONTAINER</b></dt>
</dl>
</td>
<td width="60%">
No silo is present.

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
 



