---
UID: NF:wdm.KeGetProcessorNumberFromIndex
title: KeGetProcessorNumberFromIndex function (wdm.h)
description: The KeGetProcessorNumberFromIndex routine in wdm.h converts a systemwide processor index to a group number and a group-relative processor number.
tech.root: kernel
ms.date: 01/10/2023
keywords: ["KeGetProcessorNumberFromIndex function"]
ms.keywords: KeGetProcessorNumberFromIndex, KeGetProcessorNumberFromIndex routine [Kernel-Mode Driver Architecture], k105_c0b567bd-4436-4f6a-87a2-86d8b165e2dc.xml, kernel.kegetprocessornumberfromindex, wdm/KeGetProcessorNumberFromIndex
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h, Ntddk.h, Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - KeGetProcessorNumberFromIndex
 - wdm/KeGetProcessorNumberFromIndex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeGetProcessorNumberFromIndex
---

## -description

The **KeGetProcessorNumberFromIndex** routine converts a systemwide processor index to a group number and a group-relative processor number.

## -parameters

### -param ProcIndex [in]

A systemwide processor index. If a multiprocessor system contains a total of *n* logical processors, valid processor indexes range from 0 to *n*-1.

### -param ProcNumber [out]

A pointer to a caller-allocated [**PROCESSOR_NUMBER**](../miniport/ns-miniport-_processor_number.md) structure into which the routine writes the group number and group-relative processor number of the processor that is identified by *ProcIndex*.

## -returns

**KeGetProcessorNumberFromIndex** returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER** | The *ProcIndex* parameter value is not a valid processor index. |

## -remarks

This routine accepts as input a processor index that identifies the processor across the entire multiprocessor system. The output value is a **PROCESSOR_NUMBER** structure that identifies a processor by its group number and its processor number within the group.

For example, if a multiprocessor system contains two groups, and each group contains 64 logical processors, the processor numbers in each group range from 0 to 63, but the systemwide processor indexes range from 0 to 127.

To obtain the total number of active logical processors in the system, call the [KeQueryActiveProcessorCountEx](../ntddk/nf-ntddk-kequeryactiveprocessorcountex.md) routine.

The [KeGetProcessorIndexFromNumber](../ntifs/nf-ntifs-kegetprocessorindexfromnumber.md) routine converts a group number and a group-relative processor number to a systemwide processor index.

### Examples

The following code example uses the **KeQueryActiveProcessorCountEx** and **KeGetProcessorNumberFromIndex** routines to enumerate all active logical processors in the system:

```cpp
ULONG Count;
ULONG ProcIndex;
PROCESSOR_NUMBER ProcNumber;

Count = KeQueryActiveProcessorCountEx(ALL_PROCESSOR_GROUPS);
for (ProcIndex = 0; ProcIndex < Count; ProcIndex += 1)
{
    KeGetProcessorNumberFromIndex(ProcIndex, &ProcNumber);

    // Do something with the contents of ProcNumber.
    ...
}
```

The constant value ALL_PROCESSOR_GROUPS is defined in Winnt.h and Ntdef.h.

## -see-also

[KeGetProcessorIndexFromNumber](../ntifs/nf-ntifs-kegetprocessorindexfromnumber.md)

[KeQueryActiveProcessorCountEx](../ntddk/nf-ntddk-kequeryactiveprocessorcountex.md)

[**PROCESSOR_NUMBER**](../miniport/ns-miniport-_processor_number.md)