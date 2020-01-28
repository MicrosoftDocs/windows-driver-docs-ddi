---
UID: NS:d3dkmthk._DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_2
title: _DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_2 (d3dkmthk.h)
description: Used to register the power state of a new input.
ms.assetid: e312c3ba-7a23-41e4-bebb-b19daa7a43ae
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/_DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_2"
ms.keywords: _DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_2, DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_2, *PDXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_2, *PDXGK_GRAPHICSPOWER_REGISTER_INPUT, DXGK_GRAPHICSPOWER_REGISTER_INPUT
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_2, *PDXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_2
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- _DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_2
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_2 structure

## -description

Used to register the power state of a new input.

## -struct-fields

### -field Version

The current version being used. This value must be set to one of the following DXGK_GRAPHICSPOWER_VERSIONs:

```cpp
#define DXGK_GRAPHICSPOWER_VERSION_1_0 0x1000
#define DXGK_GRAPHICSPOWER_VERSION_1_1 0x1001
#define DXGK_GRAPHICSPOWER_VERSION_1_2 0x1002
#define DXGK_GRAPHICSPOWER_VERSION DXGK_GRAPHICSPOWER_VERSION_1_2
```
By default, DXGK_GRAPHICSPOWER_VERSION represents the latest version. Graphics will support the current version and all previous versions. If this value is a version that is not recognized, we will fail with STATUS_NOINTERFACE. This should only happen in the case the non-graphics driver was built for a newer OS than what is currently running, and in this case we expect the non-graphics driver to retry with a lower version number.

DXGK_GRAPHICSPOWER_VERSION_1_1 supports F-state change notifications.
DXGK_GRAPHICSPOWER_VERSION_1_2 supports initial enumeration of shared power component data and state.

### -field PrivateHandle

An opaque handle which will be provided in any callbacks. This handle must be globally unique, therefore, a pointer to the calling driver’s PDO or FDO should be used. This handle will be used as a key by graphics to track this specific registration, and will be associated with the non-graphics driver callbacks in order to handle their future removal.

### -field PowerNotificationCb

A callback providing notification that the graphics device will be undergoing a device power state transition, and provide a new DEVICE_POWER_STATE. This callback is required to be implemented. See [PDXGK_POWER_NOTIFICATION](../d3dkmthk/nc-d3dkmthk-pdxgk_power_notification.md).

### -field RemovalNotificationCb

A callback notifying that the graphics device is being removed. Any further callbacks into graphics for this DeviceHandle will return a failing NTSTATUS code and will be blocked until you return from the RemovalNotificationCb callback. This callback is required to be implemented. See [PDXGK_REMOVAL_NOTIFICATION](../d3dkmthk/nc-d3dkmthk-pdxgk_removal_notification.md)

### -field FStateNotificationCb

Issues a state notification. This callback is optional, and is used by non-graphics drivers. See [PDXGK_FSTATE_NOTIFICATION](../d3dkmthk/nc-d3dkmthk-pdxgk_fstate_notification.md).

### -field InitialComponentStateCb

Initializes the component state. See [PDXGK_INITIAL_COMPONENT_STATE](../d3dkmthk/nc-d3dkmthk-pdxgk_initial_component_state.md).

## -remarks

Graphics drivers indicate what power components exist by responding to the queries DXGKQAITYPE_NUMPOWERCOMPONENTS and DXGKQAITYPE_POWERCOMPONENTINFO in [_DXGK_QUERYADAPTERINFOTYPE](../d3dkmddi/ne-d3dkmddi-_dxgk_queryadapterinfotype.md).

If a graphics driver registers at least one [DXGK_POWER_COMPONENT_SHARED](../d3dkmddi/ne-d3dkmddi-_dxgk_power_component_type.md) component, a GRAPHICSPOWER interface will be created for that adapter. The interface will not be registered for adapters that do not expose any of these components.

Graphics drivers can register a “blocking” component by setting the [DXGK_POWER_RUNTIME_COMPONENT](../d3dkmddi/ns-d3dkmddi-_dxgk_power_runtime_component.md) flag *ActiveInD3* to **0**, or a “nonblocking” component by setting this flag to **1**.

A blocking power component will prevent the graphics device from powering down when in use while a non-blocking power component will not. Both allow the graphics driver to properly manage its power planes when in-use by the non-graphics driver.

A graphics driver may expose both a blocking and non-blocking power component for a single physical/logical component, if it wishes to provide the ability for the non-graphics driver to selectively choose blocking or non-blocking usage.

When the GRAPHICSPOWER driver interface is available and enabled, a non-graphics driver can make an IO call to the graphics driver to register itself with the graphics driver providing and obtaining callbacks which will be used to manage the shared power components. The IO call will use the ioctl code IOCTL_INTERNAL_GRAPHICSPOWER_REGISTER, with input data **_DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_2** and output data [_DXGK_GRAPHICSPOWER_REGISTER_OUTPUT](../d3dkmthk/ns-d3dkmthk-_dxgk_graphicspower_register_output.md).

The IOCTL_INTERNAL_GRAPHICSPOWER_REGISTER code is defined as follows:

```c
#define IOCTL_INTERNAL_GRAPHICSPOWER_REGISTER \
    CTL_CODE(FILE_DEVICE_VIDEO, 0xa01, METHOD_NEITHER, FILE_ANY_ACCESS)
```
