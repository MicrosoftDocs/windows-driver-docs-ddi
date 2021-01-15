---
UID: NS:ks._KSDEVICE_THERMAL_DISPATCH
title: _KSDEVICE_THERMAL_DISPATCH (ks.h)
description: The KSDEVICE_THERMAL_DISPATCH structure is used by the miniport driver in the API call to register thermal notification callbacks. This structure contains the callback function pointers for active and passive cooling interfaces.
old-location: stream\ksdevice_thermal_dispatch.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSDEVICE_THERMAL_DISPATCH structure"]
ms.keywords: "*PKSDEVICE_THERMAL_DISPATCH, DeviceThermalState, Engaged, KSDEVICE_THERMAL_DISPATCH, KSDEVICE_THERMAL_DISPATCH structure [Streaming Media Devices], KsDevice, PKSDEVICE_THERMAL_DISPATCH, PKSDEVICE_THERMAL_DISPATCH structure pointer [Streaming Media Devices], Percentage, _KSDEVICE_THERMAL_DISPATCH, ks/KSDEVICE_THERMAL_DISPATCH, ks/PKSDEVICE_THERMAL_DISPATCH, stream.ksdevice_thermal_dispatch"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: KSDEVICE_THERMAL_DISPATCH, *PKSDEVICE_THERMAL_DISPATCH
f1_keywords:
 - _KSDEVICE_THERMAL_DISPATCH
 - ks/_KSDEVICE_THERMAL_DISPATCH
 - PKSDEVICE_THERMAL_DISPATCH
 - ks/PKSDEVICE_THERMAL_DISPATCH
 - KSDEVICE_THERMAL_DISPATCH
 - ks/KSDEVICE_THERMAL_DISPATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - _KSDEVICE_THERMAL_DISPATCH
 - PKSDEVICE_THERMAL_DISPATCH
 - KSDEVICE_THERMAL_DISPATCH
---

# _KSDEVICE_THERMAL_DISPATCH structure


## -description

The **KSDEVICE_THERMAL_DISPATCH** structure is used by the miniport driver in the API call to register thermal notification callbacks. This structure contains the callback function pointers for active and passive cooling interfaces.

## -struct-fields

### -field ActiveCooling

The active thermal callback notification.

The routine is defined as follows:

```cpp
_IRQL_requires_max_(PASSIVE_LEVEL)
typedef
void
(*PFNKSDEVICETHERMALACTIVECOOLING)(
    _In_  PKSDEVICE KsDevice,
    _In_  BOOLEAN Engaged,
    _Out_ KSDEVICE_THERMAL_STATE* DeviceThermalState
);
```

#### KsDevice

[in] A [KSDEVICE](./ns-ks-_ksdevice.md) object representing the device managed by KS.

#### Engaged

[in] Indicates whether to engage or disengage active cooling. If **TRUE**, the driver must engage active cooling (for example, by turning the fan on). If **FALSE**, the driver must disengage active cooling (for example, by turning the fan off).

#### DeviceThermalState

[out] Return value: Avstream-determined thermal state. If the state changes the pipeline is notified of the change. The pipeline notifies any app registered for thermal notifications.

### -field PassiveCooling

The passive thermal callback notification.

The routine is defined as follows:

```cpp
_IRQL_requires_max_(PASSIVE_LEVEL)
typedef
void
(*PFNKSDEVICETHERMALPASSIVECOOLING)(
    _In_  PKSDEVICE KsDevice,
    _In_  ULONG Percentage,
    _Out_ KSDEVICE_THERMAL_STATE* DeviceThermalState
);
```

#### KsDevice

[in] A [KSDEVICE](./ns-ks-_ksdevice.md) object representing the device managed by KS.

#### Percentage

[in] The percentage of full performance at which the device is permitted to operate. A parameter value of 100 indicates that the device is under no cooling restrictions and can operate at full performance level. A parameter value of zero indicates that the device must operate at its lowest thermal level. A parameter value between 0 and 100 indicates the degree to which the device's performance must be throttled to reduce heat generation. This parameter value is a threshold that the device must not exceed.

#### DeviceThermalState

[out] Return value: Avstream-determined thermal state. If the state changes the pipeline is notified of the change. The pipeline notifies any app registered for thermal notifications.

