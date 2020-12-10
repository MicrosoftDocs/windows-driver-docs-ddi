---
UID: NF:storport.StorPortMarkDumpMemory
title: StorPortMarkDumpMemory function (storport.h)
description: A miniport should mark memory used for the dump file or the hibernation file.
old-location: storage\storportmarkdumpmemory.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortMarkDumpMemory function"]
ms.keywords: MARK_DUMP_MEMORY_FLAG_PHYSICAL_ADDRESS, StorPortMarkDumpMemory, StorPortMarkDumpMemory routine [Storage Devices], storage.storportmarkdumpmemory, storport/StorPortMarkDumpMemory
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Any
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortMarkDumpMemory
 - storport/StorPortMarkDumpMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Storport.h
api_name:
 - StorPortMarkDumpMemory
---

# StorPortMarkDumpMemory function


## -description

A miniport should mark memory used for the dump file or the hibernation file. Marked memory is retained and remains valid after a resume from hibernation operation. The memory  to mark is specified by an address and range length in a call to **StorPortMarkDumpMemory**.

## -parameters

### -param HwDeviceExtension 

[in]
A pointer to the hardware device extension for the host bus adapter (HBA).

### -param Address 

[in]
The starting address of the memory range to mark.

### -param Length 

[in]
The length of the marked memory range.

### -param Flags 

[in]
Dump memory marking flags. The *Flags* parameter must be 0 or contain only the following value.

| Value | Meaning |
| ----- | ------- |
| **MARK_DUMP_MEMORY_FLAG_PHYSICAL_ADDRESS** | The address provided in *Address* is a physical address and not a system virtual address.

## -returns

**StorPortMarkDumpMemory** returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| **STOR_STATUS_SUCCESS** | Indicates that the routine set the unit attributes successfully. |
| **STOR_STATUS_INVALID_PARAMETER** | An invalid flag value was specified in the *Flags* parameter. |

## -remarks

The **StorPortMarkDumpMemory** routine must only be called by a miniport driver in its [**DriverEntry**](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) or [**HwStorFindAdapter**](nc-storport-hw_find_adapter.md) routines.

If *Length* = 0, the entire section containing *Address* is marked.

Miniport drivers should call **StorPortMarkDumpMemory** to ensure that the memory used by the miniport to generate either the dump file or the hibernation file is identified. At a minimum, miniports should call **StorPortMarkDumpMemory** when the **DumpMode** member of [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) is set to either **DUMP_MODE_MARK_MEMORY** or **DUMP_MODE_HIBER**.

## -see-also

[**DriverEntry**](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver)

[**HwStorFindAdapter**](nc-storport-hw_find_adapter.md)

[**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md)
