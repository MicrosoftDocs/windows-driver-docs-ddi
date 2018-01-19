---
UID: NF:ntddk.PsSetLoadImageNotifyRoutine
title: PsSetLoadImageNotifyRoutine function
author: windows-driver-content
description: The PsSetLoadImageNotifyRoutine routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).
old-location: kernel\pssetloadimagenotifyroutine.htm
old-project: kernel
ms.assetid: e90bc043-1b92-474c-b6c7-7e510271118b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsSetLoadImageNotifyRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PsSetLoadImageNotifyRoutine
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlPsPassive, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsSetLoadImageNotifyRoutine function



## -description
The <b>PsSetLoadImageNotifyRoutine</b> routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).



## -syntax

````
NTSTATUS PsSetLoadImageNotifyRoutine(
  _In_ PLOAD_IMAGE_NOTIFY_ROUTINE NotifyRoutine
);
````


## -parameters

### -param NotifyRoutine [in]

A pointer to the caller-implemented <a href="..\ntddk\nc-ntddk-pload_image_notify_routine.md">PLOAD_IMAGE_NOTIFY_ROUTINE</a> callback routine for load-image notifications.


## -returns
<b>PsSetLoadImageNotifyRoutine</b> either returns STATUS_SUCCESS or it returns STATUS_INSUFFICIENT_RESOURCES if it failed the callback registration.


## -remarks
Highest-level system-profiling drivers can call <b>PsSetLoadImageNotifyRoutine</b> to set up their load-image notify routines (see <a href="..\ntddk\nc-ntddk-pload_image_notify_routine.md">PLOAD_IMAGE_NOTIFY_ROUTINE</a>).

The maximum number of drivers that can be simultaneously registered to receive load-image notifications is eight. If the maximum number of load-image notify routines is already registered when a driver calls <b>PsSetLoadImageNotifyRoutine</b> to try to register an additional notify routine, <b>PsSetLoadImageNotifyRoutine</b> fails and returns STATUS_INSUFFICIENT_RESOURCES.

<b>Notes</b>

A driver must remove any callbacks it registers before it unloads. You can remove the callback by calling the <a href="..\ntddk\nf-ntddk-psremoveloadimagenotifyroutine.md">PsRemoveLoadImageNotifyRoutine</a> routine.


## -see-also
<dl>
<dt>
<a href="..\ntddk\nc-ntddk-pload_image_notify_routine.md">PLOAD_IMAGE_NOTIFY_ROUTINE</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-psgetcurrentprocessid.md">PsGetCurrentProcessId</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-psremoveloadimagenotifyroutine.md">PsRemoveLoadImageNotifyRoutine</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-pssetcreateprocessnotifyroutine.md">PsSetCreateProcessNotifyRoutine</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutine.md">PsSetCreateThreadNotifyRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsSetLoadImageNotifyRoutine routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

