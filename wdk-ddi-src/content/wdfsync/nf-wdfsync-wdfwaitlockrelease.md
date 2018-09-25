---
UID: NF:wdfsync.WdfWaitLockRelease
title: WdfWaitLockRelease function
author: windows-driver-content
description: The WdfWaitLockRelease method releases a specified wait lock.
old-location: wdf\wdfwaitlockrelease.htm
tech.root: wdf
ms.assetid: f7fb070b-fea4-48d9-8f89-1c01af183ef0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFSynchroRef_f64028b9-9f56-4d2a-8341-1b305ab02eff.xml, WdfWaitLockRelease, WdfWaitLockRelease method, kmdf.wdfwaitlockrelease, wdf.wdfwaitlockrelease, wdfsync/WdfWaitLockRelease
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfsync.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, WdfWaitlock, WdfWaitlockRelease
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfWaitLockRelease
product:
-	Windows
targetos: Windows
req.typenames: 
---

# WdfWaitLockRelease function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfWaitLockRelease</b> method releases a specified wait lock.


## -parameters




### -param Lock [in]

A handle to a framework wait-lock object, obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551171">WdfWaitLockCreate</a>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfWaitLockRelease</b> method releases a wait lock that the driver acquired by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551168">WdfWaitLockAcquire</a>.

For more information about wait locks, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.


#### Examples

For a code example that uses <b>WdfWaitLockRelease</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551168">WdfWaitLockAcquire</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551168">WdfWaitLockAcquire</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551171">WdfWaitLockCreate</a>
 

 

