---
UID: NC:pcivirt.READ_WRITE_MITIGATED_REGISTER
title: READ_WRITE_MITIGATED_REGISTER (pcivirt.h)
description: Reads or writes to mitigated address spaces.
old-location: pci\read_write_mitigated_registers.htm
tech.root: PCI
ms.date: 02/24/2018
keywords: ["READ_WRITE_MITIGATED_REGISTER callback"]
ms.keywords: "*PREAD_WRITE_MITIGATED_REGISTER, *PREAD_WRITE_MITIGATED_REGISTER callback function pointer [Buses], PCI.read_write_mitigated_registers, READ_WRITE_MITIGATED_REGISTER, ReadWriteMitigatedRegister, ReadWriteMitigatedRegister callback function [Buses], pcivirt/ReadWriteMitigatedRegister"
req.header: pcivirt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
f1_keywords:
 - READ_WRITE_MITIGATED_REGISTER
 - pcivirt/READ_WRITE_MITIGATED_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Pcivirt.h
api_name:
 - READ_WRITE_MITIGATED_REGISTER
---

# READ_WRITE_MITIGATED_REGISTER callback


## -description

Reads or writes to mitigated address spaces.

## -parameters

### -param Context [in]


A pointer to a driver-defined context.

### -param VfIndex [in]


A zero-based index of the VF to which this read/write operation applies.

### -param Read [in]




A boolean that indicates whether to perform a read or a write operation. TRUE indicates read, FALSE otherwise.

### -param BarIndex [in]


The BAR that maps the address space being mitigated.

### -param Offset [in]


The offset in number of bytes into the BAR at which this access begins.

### -param Length [in]




The length in bytes of this read or write operation.

### -param Data [in, out]


A pointer to a buffer that contains the data to read or write.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -prototype

```cpp
READ_WRITE_MITIGATED_REGISTER ReadWriteMitigatedRegister;

NTSTATUS ReadWriteMitigatedRegister(
  _In_    PVOID     Context,
  _In_    USHORT    VfIndex,
  _In_    BOOLEAN   Read,
  _In_    USHORT    BarIndex,
  _In_    ULONGLONG Offset,
  _In_    ULONG     Length,
  _Inout_ PUCHAR    Data
)
{ ... }

typedef READ_WRITE_MITIGATED_REGISTER *PREAD_WRITE_MITIGATED_REGISTER;
```

## -remarks

This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to read or write from a mitigable register.

The PF driver registers its implementation by setting the <b>ReadWriteMitigatedRegister</b> member of the <a href="/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_mitigable_device_interface">MITIGABLE_DEVICE_INTERFACE</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.

