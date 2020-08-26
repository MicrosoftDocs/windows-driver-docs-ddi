---
UID: NF:ntddk.PsSetLoadImageNotifyRoutineEx
title: PsSetLoadImageNotifyRoutineEx function (ntddk.h)
description: The PsSetLoadImageNotifyRoutineEx routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).
old-location: kernel\pssetloadimagenotifyroutineex.htm
tech.root: kernel
ms.assetid: 792cdb59-e0c2-4697-9934-b7e45a7a31a8
ms.date: 04/30/2018
keywords: ["PsSetLoadImageNotifyRoutineEx function"]
ms.keywords: PsSetLoadImageNotifyRoutineEx, PsSetLoadImageNotifyRoutineEx function [Kernel-Mode Driver Architecture], kernel.pssetloadimagenotifyroutineex, ntddk/PsSetLoadImageNotifyRoutineEx
f1_keywords:
 - "ntddk/PsSetLoadImageNotifyRoutineEx"
 - "PsSetLoadImageNotifyRoutineEx"
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
- PsSetLoadImageNotifyRoutineEx
targetos: Windows
req.typenames: 
---

# PsSetLoadImageNotifyRoutineEx function


## -description


The <b>PsSetLoadImageNotifyRoutineEx</b> routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).


## -parameters




### -param NotifyRoutine 
[in]
A pointer to the caller-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pload_image_notify_routine">PLOAD_IMAGE_NOTIFY_ROUTINE</a> callback routine for load-image notifications.


### -param Flags 
[in]
Supplies a bitmask of flags that control the callback function. Here are the possible values:

<ul>
<li>PS_IMAGE_NOTIFY_CONFLICTING_ARCHITECTURE indicates that the callback routine should be invoked for all potentially executable images, including images that have a different architecture from the native architecture of the operating system.

</li>
</ul>

## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS </b></dt>
</dl>
</td>
<td width="60%">
The callback was successfully registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
Invalid flag was supplied in <i>Flags</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The routine failed allocate a callback block due to lack of resources.

</td>
</tr>
</table>
 



## -remarks



Highest-level system-profiling drivers can call <b>PsSetLoadImageNotifyRoutineEx</b> to set up their load-image notify routines (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pload_image_notify_routine">PLOAD_IMAGE_NOTIFY_ROUTINE</a>).

The maximum number of drivers that can be simultaneously registered to receive load-image notifications is 64. If the maximum number of load-image notify routines is already registered when a driver calls <b>PsSetLoadImageNotifyRoutineEx</b> to try to register an additional notify routine, <b>PsSetLoadImageNotifyRoutineEx</b> fails and returns STATUS_INSUFFICIENT_RESOURCES.

A driver must remove any callbacks it registers before it unloads. You can remove the callback by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psremoveloadimagenotifyroutine">PsRemoveLoadImageNotifyRoutine</a> routine.
