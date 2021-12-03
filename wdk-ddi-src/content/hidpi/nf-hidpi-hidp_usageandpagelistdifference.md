---
UID: NF:hidpi.HidP_UsageAndPageListDifference
title: HidP_UsageAndPageListDifference function (hidpi.h)
description: The HidP_UsageAndPageListDifference function returns the difference between two lists of usages.
old-location: hid\hidp_usageandpagelistdifference.htm
tech.root: hid
ms.date: 12/02/2021
keywords: ["HidP_UsageAndPageListDifference function"]
ms.keywords: HidP_UsageAndPageListDifference, HidP_UsageAndPageListDifference function [Human Input Devices], hid.hidp_usageandpagelistdifference, hidfunc_0c86a540-d046-449f-a6ee-a122141fe6a3.xml, hidpi/HidP_UsageAndPageListDifference
req.header: hidpi.h
req.include-header: 
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - HidP_UsageAndPageListDifference
 - hidpi/HidP_UsageAndPageListDifference
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidpi.h
api_name:
 - HidP_UsageAndPageListDifference
---

# HidP_UsageAndPageListDifference function

## -description

The **HidP_UsageAndPageListDifference** function returns the difference between two lists of usages, as might be returned from HidP_GetUsages. In other words, it returns a list of usages that are in the current list but not the previous list as well as a list of usages that are in the previous list but not the current list.

## -parameters

### -param PreviousUsageList [in, reads]

The list of usages before.

### -param CurrentUsageList [in, reads]

The list of usages now.

### -param BreakUsageList [out, writes]

*PreviousUsageList* minus *CurrentUsageList*

### -param MakeUsageList [out, writes]

*CurrentUsageList* minus *PreviousUsageList*

### -param UsageListLength [in]

Represents the length of the usage lists in array elements. If comparing two lists with a differing number of array elements, this value is the size of the larger of the two lists. Any zero found with a list indicates an early termination of the list and any usages found after the first zero are ignored.

## -returns

**HidP_UsageAndPageListDifference** returns HIDP_STATUS_SUCCESS if the call was successful. Otherwise, it returns an [**NTSTATUS**](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.
