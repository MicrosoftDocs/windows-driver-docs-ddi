---
UID: NF:ntddk.KeLeaveCriticalRegion
title: KeLeaveCriticalRegion function (ntddk.h)
description: The KeLeaveCriticalRegion routine reenables the delivery of normal kernel-mode APCs that were disabled by a preceding call to KeEnterCriticalRegion.
old-location: kernel\keleavecriticalregion.htm
tech.root: kernel
ms.assetid: d3e90c3b-5ead-40d1-9143-a2b1fc8c255d
ms.date: 04/30/2018
ms.keywords: KeLeaveCriticalRegion, KeLeaveCriticalRegion routine [Kernel-Mode Driver Architecture], k105_f9344044-a57f-4ee4-800c-a03edcc27196.xml, kernel.keleavecriticalregion, wdm/KeLeaveCriticalRegion
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CriticalRegions, IrqlKeApcLte2, WithinCriticalRegion, HwStorPortProhibitedDDIs, WithinCriticalRegion(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeLeaveCriticalRegion
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeLeaveCriticalRegion function


## -description


The <b>KeLeaveCriticalRegion</b> routine reenables the delivery of normal kernel-mode APCs that were disabled by a preceding call to <b>KeEnterCriticalRegion</b>. 


## -parameters






## -returns



None




## -remarks



Highest-level drivers can call this routine while running in the context of the thread that requested the current I/O operation. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-keareapcsdisabled">KeAreApcsDisabled</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-keentercriticalregion">KeEnterCriticalRegion</a>
 

 

