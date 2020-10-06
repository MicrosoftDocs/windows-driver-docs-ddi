---
UID: NF:wdfsync.WdfWaitLockRelease
title: WdfWaitLockRelease function (wdfsync.h)
description: The WdfWaitLockRelease method releases a specified wait lock.
old-location: wdf\wdfwaitlockrelease.htm
tech.root: wdf
ms.assetid: f7fb070b-fea4-48d9-8f89-1c01af183ef0
ms.date: 02/26/2018
keywords: ["WdfWaitLockRelease function"]
ms.keywords: DFSynchroRef_f64028b9-9f56-4d2a-8341-1b305ab02eff.xml, WdfWaitLockRelease, WdfWaitLockRelease method, kmdf.wdfwaitlockrelease, wdf.wdfwaitlockrelease, wdfsync/WdfWaitLockRelease
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - WdfWaitLockRelease
 - wdfsync/WdfWaitLockRelease
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfWaitLockRelease
---

# WdfWaitLockRelease function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfWaitLockRelease</b> method releases a specified wait lock.

## -parameters

### -param Lock 

[in]
A handle to a framework wait-lock object, obtained by a previous call to <a href="/windows-hardware/drivers/ddi/wdfsync/nf-wdfsync-wdfwaitlockcreate">WdfWaitLockCreate</a>.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.



The <b>WdfWaitLockRelease</b> method releases a wait lock that the driver acquired by a previous call to <a href="/previous-versions/ff551168(v=vs.85)">WdfWaitLockAcquire</a>.

For more information about wait locks, see <a href="/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.


#### Examples

For a code example that uses <b>WdfWaitLockRelease</b>, see <a href="/previous-versions/ff551168(v=vs.85)">WdfWaitLockAcquire</a>.

<div class="code"></div>

## -see-also

<a href="/previous-versions/ff551168(v=vs.85)">WdfWaitLockAcquire</a>



<a href="/windows-hardware/drivers/ddi/wdfsync/nf-wdfsync-wdfwaitlockcreate">WdfWaitLockCreate</a>