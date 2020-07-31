---
UID: NF:hidpi.HidP_UsageListDifference
title: HidP_UsageListDifference function (hidpi.h)
description: The HidP_UsageListDifference routine returns the differences between two arrays of HID usages.
old-location: hid\hidp_usagelistdifference.htm
tech.root: hid
ms.assetid: 332ef453-6f9d-4cdd-a8c7-766158e540d8
ms.date: 04/30/2018
keywords: ["HidP_UsageListDifference function"]
ms.keywords: HidP_UsageListDifference, HidP_UsageListDifference routine [Human Input Devices], hid.hidp_usagelistdifference, hidfunc_91cbddd2-90f6-4784-9f1d-6d9bf8be35d3.xml, hidpi/HidP_UsageListDifference
f1_keywords:
 - "hidpi/HidP_UsageListDifference"
 - "HidP_UsageListDifference"
req.header: hidpi.h
req.include-header: Hidpi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hidparse.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Hidparse.lib
- Hidparse.dll
api_name:
- HidP_UsageListDifference
targetos: Windows
req.typenames: 
---

# HidP_UsageListDifference function


## -description


The <b>HidP_UsageListDifference</b> routine returns the differences between two arrays of <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-usages">HID usages</a>.


## -parameters




### -param PreviousUsageList [in]

Pointer to a list of usages that the routine compares with the list of usages in <i>CurrentUsageList</i>.


### -param CurrentUsageList [in]

Pointer to a list of usages that the routine compares with the list of usages in <i>PreviousUsageList</i>.


### -param BreakUsageList [out]

Pointer to a caller-allocated buffer that, on return, contains a list of the usages that are in <i>PreviousUsageList</i>, but not in <i>CurrentUsageList</i>.


### -param MakeUsageList [out]

Pointer to a caller-allocated buffer that, on return, contains a list of the usages that are in <i>CurrentUsageList</i>, but not in <i>PreviousUsageList</i>.


### -param UsageListLength [in]

Specifies the length, in array elements, of the buffers provided at <i>CurrentUsageList </i>and <i>PreviousUsageList</i>.


## -returns



<b>HidP_UsageListDifference</b> returns HIDP_STATUS_SUCCESS.




## -remarks



A user-mode application or kernel-mode driver can use this routine to compare two usage lists, for example, to determine the change in button state between two usage lists returned by two <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hdpi-h-macros">HidP_GetButtons</a> calls.

If the input usage lists have different lengths, an application or driver should set <i>UsageListLength</i> to the length of the larger list.

The routine interprets a zero usage in an input usage list as a delimiter that ends the list. Any usages after a zero in a list are not processed. Unused usages in an output list are set to zero.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff539824(v=vs.85)">HidP_UsageAndPageListDifference</a>
 

 

