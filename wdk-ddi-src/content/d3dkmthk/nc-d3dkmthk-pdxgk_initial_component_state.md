---
UID: NC:d3dkmthk.PDXGK_INITIAL_COMPONENT_STATE
title: PDXGK_INITIAL_COMPONENT_STATE
author: windows-driver-content
description: The InitialComponentStateCb callback function is implemented by the client driver to initialize the component state.
ms.assetid: 98b7dfae-6112-4d88-8580-ac3314187e22
ms.author: windowsdriverdev
ms.date:
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
topic_type:
-	apiref
api_type:
-	UserDefined
api_location:
-	d3dkmthk.h
api_name:
-	PDXGK_INITIAL_COMPONENT_STATE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PDXGK_INITIAL_COMPONENT_STATE callback function

## -description

The InitialComponentStateCb callback function is implemented by the client driver to initialize the component state.

## -prototype

```
//Declaration

PDXGK_INITIAL_COMPONENT_STATE PdxgkInitialComponentState;

// Definition

VOID PdxgkInitialComponentState
(
	PVOID GraphicsDeviceHandle
	PVOID PrivateHandle
	ULONG ComponentIndex
	BOOLEAN IsBlockingType
	UINT InitialFState
	GUID ComponentGuid
	UINT PowerComponentMappingFlag
)
{...}

PDXGK_INITIAL_COMPONENT_STATE


```

## -parameters

### -param GraphicsDeviceHandle

A handle to the graphics device.

### -param PrivateHandle

A private handle.

### -param ComponentIndex

The index of the component. Generally, this will be the index used by the graphics adapter. The exception is for LDA scenarios, where the HIWORD of the ComponentIndex indicates the adapter index, as is done when the graphics driver is called by graphics kernel for F-state changes in LDA scenarios.

### -param IsBlockingType

TRUE if the component is "blocking" (e.g. graphics driver has reported the component as ActiveInD3 = 0). Otherwise, FALSE.

### -param InitialFState

The F-state of a component represented by *ComponentIndex* at the time of the call. If an F-state transition is currently in progress, a completion notification callback (PreNotification==FALSE) [FStateNotificationCb](../d3dkmthk/nc-d3dkmthk-pdxgk_fstate_notification.md) will follow some time later when the transition completes. Depending on the timing, a PreNotification=TRUE callback may or may not occur. And if it does occur, it will precede the completion notification callback.

### -param ComponentGuid

A GUID value which is the component GUID as reported by the graphics driver for this component during its DXGKQAITYPE_POWERCOMPONENTINFO response.

### -param PowerComponentMappingFlag:

The HIWORD indicates if this is a custom driver defined value (0 = no, 1 = yes). If 0 (no), then the low word represents a DXGKMT_POWER_SHARED_TYPE enum value. These values are set by the graphics driver during its DXGKQAITYPE_POWERCOMPONENTINFO response, using the new DXGK_POWER_COMPONENT_SHARED_DESC type added to DXGK_POWER_COMPONENT_MAPPING.

## -returns

Does not return a value.

## -remarks


Upon shared power registration (IoCallDriver call), if InitialComponentStateCb was provided, it is called once for each shared power component that exists for the graphics driver has reported. The behavior of this callback is such that:

* These calls are re-entrant calls, occurring prior to IoCallDriver returning
* These calls occur at DISPATCH_LEVEL
* As these callbacks occur prior to IoCallDriver returning, [DXGK_GRAPHICSPOWER_REGISTER_OUTPUT](../d3dkmthk/ns-d3dkmthk-_dxgk_graphicspower_register_output.md) would not have been filled in yet
* If any F-state transitions are currently in progress, a post-notification FStateNotificationCb will alert the driver of the final state. Such calls will be guaranteed to occur after the InitialComponentStateCb calls. However, it is possible that such callbacks could occur prior to IoCallDriver returning if synchronization is required. A spin lock should be around IoCallDriver and the FStateNotificationCb handler.

## -see-also