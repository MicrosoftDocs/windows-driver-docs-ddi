---
UID: NF:wdm.KeLeaveGuardedRegion
title: KeLeaveGuardedRegion function
author: windows-driver-content
description: The KeLeaveGuardedRegion routine exits a guarded region entered by KeEnterGuardedRegion.
old-location: kernel\keleaveguardedregion.htm
old-project: kernel
ms.assetid: 189a3589-0d43-4f87-b889-f1f092190ffa
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeLeaveGuardedRegion, KeLeaveGuardedRegion routine [Kernel-Mode Driver Architecture], k105_a2582957-39b0-45dd-810c-7ab03d97d6a6.xml, kernel.keleaveguardedregion, wdm/KeLeaveGuardedRegion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: GuardedRegions, IrqlKeApcLte2, WithinCriticalRegion, HwStorPortProhibitedDDIs
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeLeaveGuardedRegion
product: Windows
targetos: Windows
req.typenames: 
---

# KeLeaveGuardedRegion function


## -description


The <b>KeLeaveGuardedRegion</b> routine exits a guarded region entered by <b>KeEnterGuardedRegion</b>.


## -parameters






## -returns



None




## -remarks



Guarded regions can be nested, so APCs are only reenabled once the thread exists the outermost guarded region.

For more information about guarded regions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542925">Critical Regions and Guarded Regions</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552028">KeEnterGuardedRegion</a>
 

 

