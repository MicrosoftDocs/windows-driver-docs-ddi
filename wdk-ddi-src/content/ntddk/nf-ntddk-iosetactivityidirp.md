---
UID: NF:ntddk.IoSetActivityIdIrp
title: IoSetActivityIdIrp function (ntddk.h)
description: The IoSetActivityIdIrp routine associates an activity ID with an IRP.
old-location: kernel\iosetactivityidirp.htm
tech.root: kernel
ms.assetid: 81D3BE8C-D6E0-47E2-959C-3834988E4C61
ms.date: 04/30/2018
ms.keywords: IoSetActivityIdIrp, IoSetActivityIdIrp routine [Kernel-Mode Driver Architecture], kernel.iosetactivityidirp, ntddk/IoSetActivityIdIrp
ms.topic: function
f1_keywords:
 - "ntddk/IoSetActivityIdIrp"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level if a GUID is passed in, otherwise PASSIVE_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoSetActivityIdIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoSetActivityIdIrp function


## -description


The IoSetActivityIdIrp routine associates an activity ID with an IRP.


## -parameters




### -param Irp [in]

The IRP to associate the activity ID with.


### -param Guid [in, optional]

A pointer to the GUID that represents the ID to store in the IRP.  If NULL, IoSetActivityIdIrp attempts to retrieve the activity ID from the current thread if it was the thread that originally issued the request.


## -returns



IoSetActivityIdIrp returns STATUS_SUCCESS if the call is successful. Possible error return values include the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
No GUID was provided and the ETW activity ID was unavailable.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The I/O tracing provider has not been enabled on the IRP.

</td>
</tr>
</table>
 




## -remarks



Drivers should use IoSetActivityIdIrp only on IRPs that have been allocated using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp">IoAllocateIrp</a> (and freed using <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/storport-iofreeirp">IoFreeIrp</a>). Otherwise, memory leakage may result.



