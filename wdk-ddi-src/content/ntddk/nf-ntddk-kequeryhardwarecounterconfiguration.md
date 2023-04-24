---
UID: NF:ntddk.KeQueryHardwareCounterConfiguration
title: KeQueryHardwareCounterConfiguration function (ntddk.h)
description: The KeQueryHardwareCounterConfiguration routine queries the operating system for the list of hardware counters to use for thread profiling.
tech.root: kernel
ms.date: 04/20/2023
keywords: ["KeQueryHardwareCounterConfiguration function"]
ms.keywords: KeQueryHardwareCounterConfiguration, KeQueryHardwareCounterConfiguration routine [Kernel-Mode Driver Architecture], k105_442c5acf-84a3-4078-b401-ca8cb8069c6e.xml, kernel.kequeryhardwarecounterconfiguration, ntddk/KeQueryHardwareCounterConfiguration
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeQueryHardwareCounterConfiguration
 - ntddk/KeQueryHardwareCounterConfiguration
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeQueryHardwareCounterConfiguration
---

## -description

The **KeQueryHardwareCounterConfiguration** routine queries the operating system for the list of hardware counters to use for thread profiling.

## -parameters

### -param CounterArray [out]

A pointer to a caller-allocated buffer into which the routine writes an array of elements of type [**HARDWARE_COUNTER**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_hardware_counter). Each array element is a structure that contains information about a hardware counter. The array contains one element for each hardware counter that is assigned to thread profiling. If the routine fails, it writes nothing to this buffer.

### -param MaximumCount [in]

Specifies the maximum number of elements that the routine can write to the buffer that is pointed to by the *CounterArray* parameter. The size of the caller-allocated buffer must be at least *MaximumCount* * **sizeof**(**HARDWARE_COUNTER**) bytes.

### -param Count [out]

A pointer to a location into which the routine writes the number of array elements that it has written to the buffer that is pointed to by the *CounterArray* parameter. If the buffer length that is specified by *MaximumCount* is not large enough to contain the entire array, the routine writes the required length to **Count* and returns STATUS_BUFFER_TOO_SMALL.

## -returns

**KeQueryHardwareCounterConfiguration** returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

| Return code | Description |
|--|--|
| **STATUS_BUFFER_TOO_SMALL** | The *MaximumCount* parameter specifies a buffer length that is not large enough to contain the counter configuration information. |
| **STATUS_NOT_IMPLEMENTED** | This routine is not implemented for the processor architecture that the caller is running on. |

## -remarks

In Windows 7, this routine is implemented only for the x86-based, x64-based, and Itanium-based architectures. If the caller is running on a processor architecture that is not supported, the routine returns STATUS_NOT_IMPLEMENTED.

To set the hardware counter configuration to use for thread profiling, call the [KeSetHardwareCounterConfiguration](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kesethardwarecounterconfiguration) routine.

## -see-also

[**HARDWARE_COUNTER**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_hardware_counter)

[KeSetHardwareCounterConfiguration](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kesethardwarecounterconfiguration)
