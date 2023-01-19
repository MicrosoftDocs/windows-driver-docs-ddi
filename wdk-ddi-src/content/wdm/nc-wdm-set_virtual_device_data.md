---
UID: NC:wdm.SET_VIRTUAL_DEVICE_DATA
title: SET_VIRTUAL_DEVICE_DATA (wdm.h)
description: The SetVirtualFunctionData routine writes data to the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface.
tech.root: PCI
ms.date: 01/19/2023
keywords: ["SET_VIRTUAL_DEVICE_DATA callback"]
ms.keywords: PCI.setvirtualfunctiondata, SET_VIRTUAL_DEVICE_DATA, SetVirtualFunctionData, SetVirtualFunctionData routine, wdm/SetVirtualFunctionData
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2012 and later versions of Windows.
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
req.irql: IRQL <= APC_LEVEL
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
f1_keywords:
 - SET_VIRTUAL_DEVICE_DATA
 - wdm/SET_VIRTUAL_DEVICE_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - SET_VIRTUAL_DEVICE_DATA
---

## -description

The **SetVirtualFunctionData** routine writes data to the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface.

## -parameters

### -param Context [in, out]

A pointer to interface-specific context information. The caller passes the value that is passed as the **Context** member of the [**PCI_VIRTUALIZATION_INTERFACE**](ns-wdm-pci_virtualization_interface.md) structure for the interface.

### -param VirtualFunction [in]

A zero-based value that specifies the VF on the device from which data is to be written.

### -param Buffer [in]

A pointer to the buffer that contains the configuration information to be written to the PCIe configuration space of the VF.

### -param Offset [in]

The offset into the PCIe configuration space data of the VF. This member specifies where this write operation begins.

### -param Length [in]

The length, in bytes, of the data to be written.

## -returns

The ***SetVirtualFunctionData** routine returns the length, in bytes, of the PCIe configuration data that was written after a successful write operation. If the write operation is unsuccessful, the routine returns zero.

## -remarks

The ***SetVirtualFunctionData** routine is similar to the [SetBusData](nc-wdm-get_set_device_data.md) routine, except that it writes PCIe configuration data to a VF instead of to a device's physical function (PF).

The ***SetVirtualFunctionData** routine is provided by the **GUID_PCI_VIRTUALIZATION_INTERFACE** interface. The [SetBusData](nc-wdm-get_set_device_data.md) routine is provided by the **GUID_BUS_INTERFACE_STANDARD** interface.

The virtualization stack calls ***SetVirtualFunctionData** when a driver that is running in the guest operating system calls the [SetBusData](nc-wdm-get_set_device_data.md) routine.

## -see-also

[SetBusData](nc-wdm-get_set_device_data.md)

[**PCI_VIRTUALIZATION_INTERFACE**](ns-wdm-pci_virtualization_interface.md)
