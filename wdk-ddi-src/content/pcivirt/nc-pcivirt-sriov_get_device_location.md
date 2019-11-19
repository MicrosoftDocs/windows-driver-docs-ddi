---
UID: NC:pcivirt.SRIOV_GET_DEVICE_LOCATION
title: SRIOV_GET_DEVICE_LOCATION (pcivirt.h)
description: Retrieves information about the current location of the PCI device on the bus, such as PCI Segment, Bus, Device and Function number.
old-location: pci\sriov_get_device_location.htm
tech.root: PCI
ms.assetid: 705b52e3-f695-4c58-9ae2-5a806f1e2140
ms.date: 02/24/2018
ms.keywords: "*PSRIOV_GET_DEVICE_LOCATION, *PSRIOV_GET_DEVICE_LOCATION callback function pointer [Buses], PCI.sriov_get_device_location, SRIOV_GET_DEVICE_LOCATION, SriovGetDeviceLocation, SriovGetDeviceLocation callback function [Buses], pcivirt/SriovGetDeviceLocation"
ms.topic: callback
f1_keywords:
 - "pcivirt/*PSRIOV_GET_DEVICE_LOCATION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Pcivirt.h
api_name:
- *PSRIOV_GET_DEVICE_LOCATION
product:
- Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# SRIOV_GET_DEVICE_LOCATION callback


## -description


Retrieves information about the current location of the PCI device on the bus, such as PCI Segment, Bus, Device and Function number.


## -prototype


```cpp
SRIOV_GET_DEVICE_LOCATION SriovGetDeviceLocation;

VOID SriovGetDeviceLocation(
  _In_  PVOID   Context,
  _In_  USHORT  VfIndex,
  _Out_ PUINT16 SegmentNumber,
  _Out_ PUINT8  BusNumber,
  _Out_ PUINT8  FunctionNumber
)
{ ... }

typedef SRIOV_GET_DEVICE_LOCATION *PSRIOV_GET_DEVICE_LOCATION;
```


## -parameters




### -param Context [in]

A pointer to a driver-defined context.




### -param VfIndex [in]

A zero-based index of the VF to which this read operation applies.


### -param SegmentNumber [out]

A pointer to a variable that is filled in with the current Segment Number, which describes the group of PCI Buses to which this device is attached.


### -param BusNumber [out]

A pointer to a variable that is filled in with the current Bus Number, which describes which PCI Bus to which this device is attached.


### -param FunctionNumber [out]

A pointer to a variable that is filled in with the FunctionNumber, which further describes where on this bus the device can be found.


## -remarks



This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to retrieve the device location.

The PF driver registers its implementation by setting the <b>GetDeviceLocation</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_device_interface_standard">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.



