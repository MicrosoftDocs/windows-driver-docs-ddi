---
UID: NC:d3dkmthk.PDXGK_FSTATE_NOTIFICATION
title: PDXGK_FSTATE_NOTIFICATION
author: windows-driver-content
description: Implemented by the client driver to issue a state notification.
ms.assetid: a6d6baab-576b-407d-bfb3-91b0e8f6453d
ms.date:
ms.topic: callback
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
-	PDXGK_FSTATE_NOTIFICATION
product: 
- Windows
targetos: Windows
tech.root: display
---

# PDXGK_FSTATE_NOTIFICATION callback function

## -description

Implemented by the client driver to issue a state notification.

## -prototype

```cpp
//Declaration

PDXGK_FSTATE_NOTIFICATION PdxgkFstateNotification;

// Definition

VOID PdxgkFstateNotification
(
	PVOID GraphicsDeviceHandle
	ULONG ComponentIndex
	UINT NewFState
	BOOLEAN PreNotification
	PVOID PrivateHandle
)
{...}

```

## -parameters

### -param GraphicsDeviceHandle:

An opaque handle which should be provided when making callbacks to the graphics device.

### -param ComponentIndex:

The index of the component. Generally, this will be the index used by the graphics adapter. The exception is for LDA scenarios, where the HIWORD of the ComponentIndex indicates the adapter index, as is done when the graphics driver is called by graphics kernel for F-state changes in LDA scenarios.

### -param NewFState:

The F-state to transition to.

### -param PreNotification:

Indicates that a notification should be provided.

### -param PrivateHandle:

An opaque handle which will be provided in any callbacks. This handle must be globally unique, therefore, a pointer to the calling driver’s PDO or FDO should be used.

## -returns

Returns VOID.

## -remarks

All callbacks made from Dxgkrnl to this callback may be called at up to DISPATCH_LEVEL (e.g., the non-graphics driver should not block on any of these notifications). Callbacks will only be made for [DXGK_POWER_COMPONENT_SHARED](../d3dkmddi/ne-d3dkmddi-_dxgk_power_component_type.md) type power components.

Pre-notifications will be provided prior to transitioning F-states. Completion notification callbacks (PreNotification==FALSE) are issued as part of the graphics driver’s [DxgkCbCompleteFStateTransition](../d3dkmddi/nc-d3dkmddi-dxgkcb_completefstatetransition.md) callback. That is, all shared power components will be notified of the F-state transition completion prior to DxgkCbCompleteFStateTransition returning.



## -see-also
