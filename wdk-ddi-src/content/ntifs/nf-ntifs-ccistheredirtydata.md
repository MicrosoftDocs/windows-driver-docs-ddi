---
UID: NF:ntifs.CcIsThereDirtyData
title: CcIsThereDirtyData function (ntifs.h)
description: The CcIsThereDirtyData routine determines whether a mounted volume contains any files that have dirty data in the system cache.
old-location: ifsk\ccistheredirtydata.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["CcIsThereDirtyData function"]
ms.keywords: CcIsThereDirtyData, CcIsThereDirtyData routine [Installable File System Drivers], ccref_86c4a327-a13e-49b3-89d1-abf976973000.xml, ifsk.ccistheredirtydata, ntifs/CcIsThereDirtyData
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - CcIsThereDirtyData
 - ntifs/CcIsThereDirtyData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcIsThereDirtyData
---

# CcIsThereDirtyData function


## -description

The <b>CcIsThereDirtyData</b> routine determines whether a mounted volume contains any files that have dirty data in the system cache.

## -parameters

### -param Vpb [in]


Pointer to a volume parameter block (VPB) for the volume.

## -returns

<b>CcIsThereDirtyData</b> returns <b>TRUE</b> if the volume contains one or more cached files whose data has been modified in the cache but not yet flushed to disk, <b>FALSE</b> otherwise.

## -remarks

<b>CcIsThereDirtyData</b> ignores temporary files.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccflushcache">CcFlushCache</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpurgecachesection">CcPurgeCacheSection</a>
