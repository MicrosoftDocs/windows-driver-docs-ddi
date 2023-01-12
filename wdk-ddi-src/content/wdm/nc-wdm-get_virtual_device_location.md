---
UID: NC:wdm.GET_VIRTUAL_DEVICE_LOCATION
title: GET_VIRTUAL_DEVICE_LOCATION (wdm.h)
description: The GetLocation routine returns the device location of a PCI Express (PCIe) virtual function (VF) on a PCI bus. A device that supports the single root I/O virtualization (SR-IOV) interface can expose one or more VFs on the PCI bus.
tech.root: PCI
ms.date: 01/06/2023
keywords: ["GET_VIRTUAL_DEVICE_LOCATION callback"]
ms.keywords: GET_VIRTUAL_DEVICE_LOCATION, GetLocation, GetLocation routine, PCI.getlocation, wdm/GetLocation
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2012 and later versions of Windows Server.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
f1_keywords:
 - GET_VIRTUAL_DEVICE_LOCATION
 - wdm/GET_VIRTUAL_DEVICE_LOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - GET_VIRTUAL_DEVICE_LOCATION
---

# GET_VIRTUAL_DEVICE_LOCATION callback

## -description

The **GetLocation** routine returns the device location of a PCI Express (PCIe) virtual function (VF) on a PCI bus. A device that supports the single root I/O virtualization (SR-IOV) interface can expose one or more VFs on the PCI bus.

## -parameters

### -param Context [in, out]

A pointer to interface-specific context information. The caller passes the value that is passed as the **Context** member of the [**PCI_VIRTUALIZATION_INTERFACE**](./ns-wdm-pci_virtualization_interface.md) structure for the interface.

### -param VirtualFunction [in]

A zero-based value that specifies the VF on the device for  which the device location is returned

### -param SegmentNumber [out]

A pointer to a caller-supplied variable in which this routine returns a UINT16 value for the current PCI segment number. This value specifies the group of PCI buses on which the device is attached.

### -param BusNumber [out]

A pointer to a caller-supplied variable in which this routine returns a UINT8 value. This value specifies the current PCI bus number on which the device is attached.

### -param FunctionNumber [out]

A pointer to a caller-supplied variable in which this routine returns a UINT8 value.  This value contains the function number for the specified VF on the PCI bus.

## -returns

The **GetLocation** routine returns one of the following NTSTATUS values:

| Return code | Description |
|---|---|
| **STATUS_SUCCESS** | The operation completed successfully. |
| **STATUS_INVALID_PARAMETER** | The *VirtualFunction* parameter is larger than the value of the **TotalVFs** member of the SR-IOV Extended Capability structure for the device. |

## -prototype

```cpp
GET_VIRTUAL_DEVICE_LOCATION GetLocation;

NTSTATUS GetLocation(
  _Inout_ PVOID   Context,
  _In_    USHORT  VirtualFunction,
  _Out_   PUINT16 SegmentNumber,
  _Out_   PUINT8  BusNumber,
  _Out_   PUINT8  FunctionNumber
)
{ ... }
```

## -remarks

The **GetLocation** routine returns the current device location of a VF  in the PCIe hierarchy. This information is necessary for a virtualization system that is using an I/O memory management unit (IOMMU) to route traffic to or from the device.

Upon a successful return from a call to the **GetLocation** routine, the *FunctionNumber* parameter contains a value that represents the function number for the specified VF on the PCI bus. This value is based on the Alternative Routing Interpretation (ARI) option of the PCI Express 3.0 specification.  ARI treats a PCIe bus as a single device with an 8-bit function space, which allows for 256 functions on the bus.

The **GetLocation** routine is provided by the **GUID_PCI_VIRTUALIZATION_INTERFACE** interface.

The PCI bus number on which the VF is located can change. We do not recommend that drivers store the device location for a VF in nonvolatile storage such as the registry.

## -see-also

[**PCI_VIRTUALIZATION_INTERFACE**](./ns-wdm-pci_virtualization_interface.md)