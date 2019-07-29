---
UID: NF:ntifs.CcIsThereDirtyDataEx
title: CcIsThereDirtyDataEx function (ntifs.h)
description: The CcIsThereDirtyDataEx routine determines whether a volume contains any files that have dirty data in the system cache.
old-location: ifsk\ccistheredirtydataex.htm
tech.root: ifsk
ms.assetid: 88378f82-2975-4b53-9dde-53ab81df3c53
ms.date: 04/16/2018
ms.keywords: CcIsThereDirtyDataEx, CcIsThereDirtyDataEx routine [Installable File System Drivers], ccref_13ae1f3e-b2ea-4bc6-a1cb-0101afd58d04.xml, ifsk.ccistheredirtydataex, ntifs/CcIsThereDirtyDataEx
ms.topic: function
f1_keywords:
 - "ntifs/CcIsThereDirtyDataEx"
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- CcIsThereDirtyDataEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# CcIsThereDirtyDataEx function


## -description


The <b>CcIsThereDirtyDataEx</b> routine determines whether a volume contains any files that have dirty data in the system cache.


## -parameters




### -param Vpb [in]

A pointer to a volume parameter block (VPB) for the volume. 


### -param NumberOfDirtyPages [in, optional]

An optional pointer to an unsigned long buffer that receives the number of dirty pages on the volume (associated with the Vpb parameter). 


## -returns



The <b>CcIsThereDirtyDataEx</b> routine returns <b>TRUE</b> if the volume contains one or more cached files whose data has been modified in the cache, but not yet flushed to disk. Otherwise, this routine returns <b>FALSE</b>.




## -remarks



This routine will return <b>TRUE</b> if any dirty pages exist including temporary files (<a href="https://msdn.microsoft.com/library/windows/hardware/ff539145">CcIsThereDirtyData</a> ignores temporary files).  It will also return <b>TRUE</b> if there is any data currently queued to the volume.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539082">CcFlushCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539145">CcIsThereDirtyData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539188">CcPurgeCacheSection</a>
 

 

