---
UID: NF:ntifs.MmPrefetchPages
title: MmPrefetchPages function (ntifs.h)
description: The MmPrefetchPages routine reads groups of pages from secondary storage in the optimal fashion.
old-location: ifsk\mmprefetchpages.htm
tech.root: ifsk
ms.assetid: fd76dfed-2c47-4289-a672-1db8129f5a9e
ms.date: 08/21/2020
keywords: ["MmPrefetchPages function"]
ms.keywords: MmPrefetchPages, MmPrefetchPages routine [Installable File System Drivers], ifsk.mmprefetchpages, mmref_6e555336-a134-409a-9c8a-a4a217e38599.xml, ntifs/MmPrefetchPages
req.header: ntifs.h
req.include-header: Ntifs.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
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
 - MmPrefetchPages
 - ntifs/MmPrefetchPages
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmPrefetchPages
---

# MmPrefetchPages function


## -description

The **MmPrefetchPages** routine reads groups of pages from secondary storage in the optimal fashion.

## -parameters

### -param NumberOfLists

[in] The number of read-lists in the array passed in the *ReadLists* parameter.

### -param ReadLists

[in] A pointer to an array of read-lists to be prefetched.

## -returns

**MmPrefetchPages** returns STATUS_SUCCESS or an appropriate error status representing the final completion status of the operation. Possible error status codes include the following:

| Return code | Description |
| ----------- | ----------- |
| **STATUS_INSUFFICIENT_RESOURCES** | A temporary buffer required by this function could not be allocated. |
| **STATUS_INVALID_PARAMETER_1**    | A section in *ReadLists* is not prefetchable (for example, a physical or pagefile-backed section), or an invalid *NumberOfLists* value was provided. |

**MmPrefetchPages** returns STATUS_SUCCESS on success and also if all of the requested pages were already in memory indicating no reads from secondary storage were required.

## -remarks

**MmPrefetchPages** reads pages from secondary storage described in the read-lists in the optimal fashion. The caller builds a list of various file objects and logical block offsets, passing them to the **MmPrefetchPages** function which examines the internal pages, reading in those that are not already valid or in transition. The pages are read with a single read, using a dummy page to bridge small gaps. If the gap is "large", then separate reads are issued.

> [!NOTE]
>
> The [section object](/windows-hardware/drivers/kernel/section-objects-and-views) must already exist for the file to be prefetched. A section handle can be obtained by calling [**ZwCreateSection**](../wdm/nf-wdm-zwcreatefile.md).