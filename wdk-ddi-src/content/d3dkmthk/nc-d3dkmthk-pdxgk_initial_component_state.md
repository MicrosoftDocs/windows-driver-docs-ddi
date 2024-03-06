---
UID: NC:d3dkmthk.PDXGK_INITIAL_COMPONENT_STATE
title: PDXGK_INITIAL_COMPONENT_STATE (d3dkmthk.h)
description: The InitialComponentStateCb callback function is implemented by the client driver to initialize the component state.
ms.date: 10/07/2022
keywords: ["PDXGK_INITIAL_COMPONENT_STATE callback function"]
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: engagement-fy23
f1_keywords:
 - PDXGK_INITIAL_COMPONENT_STATE
 - d3dkmthk/PDXGK_INITIAL_COMPONENT_STATE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PDXGK_INITIAL_COMPONENT_STATE
---

# PDXGK_INITIAL_COMPONENT_STATE callback function

## -description

The **PDXGK_INITIAL_COMPONENT_STATE** callback function is implemented by the client driver to initialize the component state.

## -parameters

### -param GraphicsDeviceHandle

A handle to the graphics device.

### -param PrivateHandle

An opaque handle provided in any callbacks. This handle must be globally unique, therefore, a pointer to the calling driver’s PDO or FDO should be used.

### -param ComponentIndex

The index of the component. Generally, this will be the index used by the graphics adapter. The exception is for linked display adapter (LDA) scenarios, where the HIWORD of the **ComponentIndex** indicates the adapter index, as is done when the graphics driver is called by the graphics kernel for F-state changes in LDA scenarios.

### -param IsBlockingType

Set TRUE if the component is "blocking"; for example, the graphics driver has reported the component as [**ActiveInD3**](../d3dkmddi/ns-d3dkmddi-_dxgk_power_component_flags.md) = 0. Otherwise, set FALSE.

### -param InitialFState

The F-state of a component represented by **ComponentIndex** at the time of the call. If an F-state transition is currently in progress, a [**PDXGK_FSTATE_NOTIFICATION**](../d3dkmthk/nc-d3dkmthk-pdxgk_fstate_notification.md) completion notification callback with ```PreNotification=FALSE``` will follow some time later when the transition completes. Depending on the timing, a ```PreNotification=TRUE``` callback might occur. If it does occur, it will precede the completion notification callback.

### -param ComponentGuid

A GUID value which is the component GUID as reported by the graphics driver for this component during its [**DXGKQAITYPE_POWERCOMPONENTINFO**](../d3dkmddi/ne-d3dkmddi-_dxgk_queryadapterinfotype.md) response.

### -param PowerComponentMappingFlag

The HIWORD indicates if this is a custom driver defined value (0 = no, 1 = yes). If 0 (no), then the low word represents a [**DXGKMT_POWER_SHARED_TYPE**](ne-d3dkmthk-_dxgkmt_power_shared_type.md) enum value. These values are set by the graphics driver during its [**DXGKQAITYPE_POWERCOMPONENTINFO**](../d3dkmddi/ne-d3dkmddi-_dxgk_queryadapterinfotype.md) response, using the **DXGK_POWER_COMPONENT_SHARED_DESC** type added to [**DXGK_POWER_COMPONENT_MAPPING**](../d3dkmddi/ns-d3dkmddi-_dxgk_power_component_mapping.md).

## -remarks

Upon shared power registration ([**IoCallDriver**](../wdm/nf-wdm-iocalldriver.md) call), if **PDXGK_INITIAL_COMPONENT_STATE** was provided, it is called once for each shared power component that the graphics driver has reported. The behavior of this callback is such that:

* These calls are re-entrant calls, occurring prior to **IoCallDriver** returning
* These calls occur at [DISPATCH_LEVEL, which requires driver code and data to be memory-resident](/windows-hardware/drivers/kernel/when-should-code-and-data-be-pageable-)
* As these callbacks occur prior to **IoCallDriver** returning, [**DXGK_GRAPHICSPOWER_REGISTER_OUTPUT**](../d3dkmthk/ns-d3dkmthk-_dxgk_graphicspower_register_output.md) would not have been filled in yet
* If any F-state transitions are currently in progress, a post-notification [**PDXGK_FSTATE_NOTIFICATION**](../d3dkmthk/nc-d3dkmthk-pdxgk_fstate_notification.md) will alert the driver of the final state. Such calls will be guaranteed to occur after the InitialComponentStateCb calls. However, it is possible that such callbacks could occur prior to **IoCallDriver** returning if synchronization is required. A spin lock should be around **IoCallDriver** and the **PDXGK_FSTATE_NOTIFICATION** handler.

## -see-also

[**DXGK_GRAPHICSPOWER_REGISTER_OUTPUT**](../d3dkmthk/ns-d3dkmthk-_dxgk_graphicspower_register_output.md)

[**DXGK_POWER_COMPONENT_MAPPING**](../d3dkmddi/ns-d3dkmddi-_dxgk_power_component_mapping.md)

[**DXGK_QUERYADAPTERINFOTYPE**](../d3dkmddi/ne-d3dkmddi-_dxgk_queryadapterinfotype.md)

[**DXGKMT_POWER_SHARED_TYPE**](ne-d3dkmthk-_dxgkmt_power_shared_type.md)

[**PDXGK_FSTATE_NOTIFICATION**](../d3dkmthk/nc-d3dkmthk-pdxgk_fstate_notification.md)
