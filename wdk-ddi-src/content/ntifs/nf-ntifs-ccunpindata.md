---
UID: NF:ntifs.CcUnpinData
title: CcUnpinData function (ntifs.h)
description: The CcUnpinData routine releases cached file data that was mapped or pinned by an earlier call to CcMapData, CcPinRead, or CcPreparePinWrite.
old-location: ifsk\ccunpindata.htm
tech.root: ifsk
ms.assetid: a06bbe25-9841-4aeb-9d51-257dd1472027
ms.date: 04/16/2018
keywords: ["CcUnpinData function"]
ms.keywords: CcUnpinData, CcUnpinData routine [Installable File System Drivers], ccref_ba560a38-4d3b-409f-b1ea-19c3a117615e.xml, ifsk.ccunpindata, ntifs/CcUnpinData
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CcUnpinData
 - ntifs/CcUnpinData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcUnpinData
---

# CcUnpinData function


## -description

The <b>CcUnpinData</b> routine releases cached file data that was mapped or pinned by an earlier call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccmapdata">CcMapData</a>, <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpinread">CcPinRead</a>, or <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparepinwrite">CcPreparePinWrite</a>.

## -parameters

### -param Bcb 

[in]
Pointer to a buffer control block (BCB) for the data to be released.

## -remarks

<b>CcUnpinData</b> frees the BCB and performs any other necessary cleanup.

Every successful call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccmapdata">CcMapData</a>, <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpinread">CcPinRead</a>, or <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparepinwrite">CcPreparePinWrite</a> must be matched by a subsequent call to <b>CcUnpinData</b>. 

BCBs that have been modified by <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccsetbcbownerpointer">CcSetBcbOwnerPointer</a> cannot be unpinned by calling <b>CcUnpinData</b>. <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccunpindataforthread">CcUnpinDataForThread</a> must be called instead.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccmapdata">CcMapData</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpinread">CcPinRead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparepinwrite">CcPreparePinWrite</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccsetbcbownerpointer">CcSetBcbOwnerPointer</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccunpindataforthread">CcUnpinDataForThread</a>