---
UID: NF:ntddk.PsSetLoadImageNotifyRoutine
title: PsSetLoadImageNotifyRoutine function (ntddk.h)
description: The PsSetLoadImageNotifyRoutine routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).
old-location: kernel\pssetloadimagenotifyroutine.htm
tech.root: kernel
ms.assetid: e90bc043-1b92-474c-b6c7-7e510271118b
ms.date: 04/30/2018
keywords: ["PsSetLoadImageNotifyRoutine function"]
ms.keywords: PsSetLoadImageNotifyRoutine, PsSetLoadImageNotifyRoutine routine [Kernel-Mode Driver Architecture], k108_287b9d79-8b77-40b6-8fe7-21ac3551e437.xml, kernel.pssetloadimagenotifyroutine, ntddk/PsSetLoadImageNotifyRoutine
f1_keywords:
 - "ntddk/PsSetLoadImageNotifyRoutine"
 - "PsSetLoadImageNotifyRoutine"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PsSetLoadImageNotifyRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsSetLoadImageNotifyRoutine function


## -description


The <b>PsSetLoadImageNotifyRoutine</b> routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).


## -parameters




### -param NotifyRoutine [in]

A pointer to the caller-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pload_image_notify_routine">PLOAD_IMAGE_NOTIFY_ROUTINE</a> callback routine for load-image notifications.


## -returns



<b>PsSetLoadImageNotifyRoutine</b> either returns STATUS_SUCCESS or it returns STATUS_INSUFFICIENT_RESOURCES if it failed the callback registration.




## -remarks



Highest-level system-profiling drivers can call <b>PsSetLoadImageNotifyRoutine</b> to set up their load-image notify routines (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pload_image_notify_routine">PLOAD_IMAGE_NOTIFY_ROUTINE</a>).

The maximum number of drivers that can be simultaneously registered to receive load-image notifications is eight. If the maximum number of load-image notify routines is already registered when a driver calls <b>PsSetLoadImageNotifyRoutine</b> to try to register an additional notify routine, <b>PsSetLoadImageNotifyRoutine</b> fails and returns STATUS_INSUFFICIENT_RESOURCES.

<b>Notes</b>

<ul>
<li>An update for Windows 8.1 increases the maximum number of drivers registered to receive load-image notifications from eight to 64. This update is installed as part of a cumulative update that is available through Windows Update starting on April 8, 2014. In addition, this cumulative update is available at <a href="https://support.microsoft.com/help/2919355/windows-rt-8-1-windows-8-1-and-windows-server-2012-r2-update-april-201">https://support.microsoft.com/kb/2919355</a>.</li>
<li>Users of Windows 7 with Service Pack 1 (SP1) can install a hotfix to increase the maximum number of drivers registered to receive load-image notifications from eight to 64. This hotfix is available at <a href="https://support.microsoft.com/help/2922790/some-software-products-function-incorrectly-in-windows">https://support.microsoft.com/kb/2922790</a>.</li>
</ul>
A driver must remove any callbacks it registers before it unloads. You can remove the callback by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psremoveloadimagenotifyroutine">PsRemoveLoadImageNotifyRoutine</a> routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pload_image_notify_routine">PLOAD_IMAGE_NOTIFY_ROUTINE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentprocessid">PsGetCurrentProcessId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psremoveloadimagenotifyroutine">PsRemoveLoadImageNotifyRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutine">PsSetCreateProcessNotifyRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutine">PsSetCreateThreadNotifyRoutine</a>
 

 

