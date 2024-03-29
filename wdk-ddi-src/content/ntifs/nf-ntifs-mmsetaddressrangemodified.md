---
UID: NF:ntifs.MmSetAddressRangeModified
title: MmSetAddressRangeModified function (ntifs.h)
description: The MmSetAddressRangeModified routine marks currently valid pages in the specified range of the system cache as modified.
old-location: ifsk\mmsetaddressrangemodified.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["MmSetAddressRangeModified function"]
ms.keywords: MmSetAddressRangeModified, MmSetAddressRangeModified routine [Installable File System Drivers], ifsk.mmsetaddressrangemodified, mmref_4d6ef497-4a72-4fed-8422-365708740cc7.xml, ntifs/MmSetAddressRangeModified
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
req.irql: See Remarks section
targetos: Windows
req.typenames: 
f1_keywords:
 - MmSetAddressRangeModified
 - ntifs/MmSetAddressRangeModified
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmSetAddressRangeModified
---

# MmSetAddressRangeModified function


## -description

The <b>MmSetAddressRangeModified</b> routine marks currently valid pages in the specified range of the system cache as modified.

## -parameters

### -param Address [in]


Address of the start of the range.

### -param Length [in]


Length of the range in bytes.

## -returns

<b>MmSetAddressRangeModified</b> returns <b>TRUE</b> if it marked at least one page in the range as modified, <b>FALSE</b> otherwise.

## -remarks

The entire range specified by <i>Address</i> and <i>Length</i> must reside within the system cache.

For more information about memory management, see <a href="/windows-hardware/drivers/kernel/managing-memory-for-drivers">Memory Management</a>. 

Callers of <b>MmSetAddressRangeModified</b> must be running at IRQL < DISPATCH_LEVEL for pageable addresses, and IRQL <= DISPATCH_LEVEL for nonpageable addresses.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccistheredirtydata">CcIsThereDirtyData</a>
