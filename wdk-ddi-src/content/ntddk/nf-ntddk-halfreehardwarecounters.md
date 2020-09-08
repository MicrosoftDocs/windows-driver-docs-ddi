---
UID: NF:ntddk.HalFreeHardwareCounters
title: HalFreeHardwareCounters function (ntddk.h)
description: The HalFreeHardwareCounters routine frees a set of hardware performance counters that was acquired in a previous call to HalAllocateHardwareCounters routine.
old-location: kernel\halfreehardwarecounters.htm
tech.root: kernel
ms.assetid: 646a073b-e0c5-4d41-b60c-3935c129fb39
ms.date: 02/16/2018
keywords: ["HalFreeHardwareCounters function"]
ms.keywords: ",  , C, F, H, HalFreeHardwareCounters, HalFreeHardwareCounters routine [Kernel-Mode Driver Architecture], a, d, e, k103_7516fb8d-7064-4f4a-bbef-a979809bf011.xml, kernel.halfreehardwarecounters, l, n, ntddk/HalFreeHardwareCounters, o, r, s, t, u, w"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.lib: Hal.lib
req.dll: Hal.dll
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
ms.custom: 19H1
f1_keywords:
 - HalFreeHardwareCounters
 - ntddk/HalFreeHardwareCounters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hal.dll
api_name:
 - HalFreeHardwareCounters
---

# HalFreeHardwareCounters function


## -description

The <b>HalFreeHardwareCounters</b> routine frees a set of hardware performance counter resources that was acquired in a previous call to [**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md) routine.

## -parameters

### -param CounterSetHandle 

[in]
A handle to the allocated counter resources. The caller acquired this handle in a previous call to [**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md).

## -returns

<b>HalFreeHardwareCounters</b> returns STATUS_SUCCESS if the call was successful. Possible error return values include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameter <i>CounterSetHandle</i> is not a valid counter resources handle.

</td>
</tr>
</table>

## -syntax

```cpp
NTSTATUS HalFreeHardwareCounters(
  _In_ HANDLE CounterSetHandle
);
```

## -remarks

Before calling this function, the client driver is expected to stop and clear the associated counter resources.

## -see-also

[**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md)

