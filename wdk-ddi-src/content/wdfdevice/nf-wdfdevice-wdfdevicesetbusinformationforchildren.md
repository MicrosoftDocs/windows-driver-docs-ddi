---
UID: NF:wdfdevice.WdfDeviceSetBusInformationForChildren
title: WdfDeviceSetBusInformationForChildren function (wdfdevice.h)
description: The WdfDeviceSetBusInformationForChildren method sets information about a bus that a bus driver supports. This information is available to the bus's child devices.
old-location: wdf\wdfdevicesetbusinformationforchildren.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfDeviceSetBusInformationForChildren function"]
ms.keywords: DFDeviceObjectGeneralRef_76b69a67-0e1e-41d6-be98-3d5f76433d97.xml, WdfDeviceSetBusInformationForChildren, WdfDeviceSetBusInformationForChildren method, kmdf.wdfdevicesetbusinformationforchildren, wdf.wdfdevicesetbusinformationforchildren, wdfdevice/WdfDeviceSetBusInformationForChildren
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceSetBusInformationForChildren
 - wdfdevice/WdfDeviceSetBusInformationForChildren
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceSetBusInformationForChildren
---

# WdfDeviceSetBusInformationForChildren function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceSetBusInformationForChildren</b> method sets information about a bus that a bus driver supports. This information is available to the bus's child devices.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param BusInformation 

[in]
A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pnp_bus_information">PNP_BUS_INFORMATION</a> structure that describes the bus.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.




Child devices can obtain the information that <b>WdfDeviceSetBusInformationForChildren</b> supplies by calling <a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitqueryproperty">WdfFdoInitQueryProperty</a> or <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicequeryproperty">WdfDeviceQueryProperty</a>.


#### Examples

The following code example initializes a PNP_BUS_INFORMATION structure and then calls <b>WdfDeviceSetBusInformationForChildren</b>.

```cpp
PNP_BUS_INFORMATION  busInfo;

busInfo.BusTypeGuid = GUID_DEVCLASS_TOASTER;
busInfo.LegacyBusType = PNPBus;
busInfo.BusNumber = 0;

WdfDeviceSetBusInformationForChildren(
                                      device,
                                      &busInfo
                                      );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pnp_bus_information">PNP_BUS_INFORMATION</a>
