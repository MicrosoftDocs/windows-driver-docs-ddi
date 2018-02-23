---
UID: NF:ntddk.PsSetLoadImageNotifyRoutineEx
title: PsSetLoadImageNotifyRoutineEx function
author: windows-driver-content
description: The PsSetLoadImageNotifyRoutineEx routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).
old-location: kernel\pssetloadimagenotifyroutineex.htm
old-project: kernel
ms.assetid: 792cdb59-e0c2-4697-9934-b7e45a7a31a8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddk/PsSetLoadImageNotifyRoutineEx, kernel.pssetloadimagenotifyroutineex, PsSetLoadImageNotifyRoutineEx function [Kernel-Mode Driver Architecture], PsSetLoadImageNotifyRoutineEx
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PsSetLoadImageNotifyRoutineEx
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsSetLoadImageNotifyRoutineEx function


## -description


The <b>PsSetLoadImageNotifyRoutineEx</b> routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).


## -syntax


````
 NTSTATUS  PsSetLoadImageNotifyRoutineEx(
  _In_ PLOAD_IMAGE_NOTIFY_ROUTINE NotifyRoutine,
  _In_ ULONG_PTR                  Flags
);
````


## -parameters




### -param NotifyRoutine [in]

A pointer to the caller-implemented <a href="..\ntddk\nc-ntddk-pload_image_notify_routine.md">PLOAD_IMAGE_NOTIFY_ROUTINE</a> callback routine for load-image notifications.


### -param Flags [in]

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
 



