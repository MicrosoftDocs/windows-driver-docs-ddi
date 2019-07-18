---
UID: NF:storport.StorPortGetDeviceBase
title: StorPortGetDeviceBase function (storport.h)
description: The StorPortGetDeviceBase routine maps an I/O address to system address space.
old-location: storage\storportgetdevicebase.htm
tech.root: storage
ms.assetid: 6d25f2fb-be77-480f-b07c-294ab8a4272e
ms.date: 03/29/2018
ms.keywords: StorPortGetDeviceBase, StorPortGetDeviceBase routine [Storage Devices], storage.storportgetdevicebase, storport/StorPortGetDeviceBase, storprt_8be3e3d9-dae5-49cb-aa44-31d3be745045.xml
ms.topic: function
f1_keywords:
 - "storport/StorPortGetDeviceBase"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortGetDeviceBase
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortGetDeviceBase function

## -description

The **StorPortGetDeviceBase** routine maps an I/O address to system address space. 

## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls [StorPortInitialize](nf-storport-storportinitialize.md). The port driver frees this memory when it removes the device.

### -param BusType [in]

Specifies the interface type of the I/O bus on which the HBA is connected. The miniport driver's [HwStorFindAdapter](nc-storport-hw_find_adapter.md) routine obtains the value for this parameter from the **AdapterInterfaceType** member of the input [PORT_CONFIGURATION_INFORMATION](ns-storport-_port_configuration_information.md).

### -param SystemIoBusNumber [in]

Specifies the system-assigned number of the I/O bus on which the HBA is connected. The [HwStorFindAdapter](nc-storport-hw_find_adapter.md) routine obtains the value for this parameter from the **SystemIoBusNumber** member of the input [PORT_CONFIGURATION_INFORMATION](ns-storport-_port_configuration_information.md).

### -param IoAddress [in]

Specifies the bus-relative base address of a range used by the HBA. The [HwStorFindAdapter](nc-storport-hw_find_adapter.md) routine obtains the value for this parameter from one of the **AccessRanges** elements in the [PORT_CONFIGURATION_INFORMATION](ns-storport-_port_configuration_information.md) if the port driver supplies range-configuration information. Otherwise, this address can be a value returned by [StorPortGetBusData](nf-storport-storportgetbusdata.md) or a miniport driver-supplied default value. Avoid using a base address of zero because its successful return status can conflict with the error status (**NULL**).

### -param NumberOfBytes [in]

Specifies the size in bytes of the range that the mapping should cover. The [HwStorFindAdapter](nc-storport-hw_find_adapter.md) routine obtains the value of this parameter from the same **AccessRanges** element as *IoAddress* if the port driver supplies range configuration information. Otherwise, this value can be returned by [StorPortGetBusData](nf-storport-storportgetbusdata.md) or a miniport driver-supplied default. In any case, the driver must not access the hardware outside of the returned, mapped range.

### -param InIoSpace [in]

TRUE indicates the range to be mapped is in I/O space, and the miniport driver will pass mapped addresses in this range to the Storport *port* read/write routines to communicate with the HBA. The [HwStorFindAdapter](nc-storport-hw_find_adapter.md) routine obtains the value of this parameter from the same **AccessRanges** element as *IoAddress*. Note that a miniport driver *must invert* the value of the **InMemorySpace** member in an ACCESS_RANGE-type element before it is passed to **StorPortGetDeviceBase** as the *InIoSpace* argument. **FALSE** indicates that the range to be mapped is in memory space.

## -returns

A mapped, logical base address corresponding to the bus-relative address supplied in the *IoAddress* parameter. 

## -remarks

Every miniport driver must pass mapped, logical access range addresses to the Storport *port* read/write routines and the Storport *register* read/write routines when communicating with its HBA(s).

This routine supports only those addresses that were assigned to the driver by the system Plug and Play (PnP) manager.

## -see-also

[StorPortFreeDeviceBase](nf-storport-storportfreedevicebase.md)
