---
UID: NC:d3dkmddi.DXGKCB_COMPLETEFSTATETRANSITION
title: DXGKCB_COMPLETEFSTATETRANSITION (d3dkmddi.h)
description: Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to notify the port driver that a power component has completed the F-state transition.
old-location: display\dxgkcbcompletefstatetransition.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_COMPLETEFSTATETRANSITION callback function"]
ms.keywords: DXGKCB_COMPLETEFSTATETRANSITION, DXGKCB_COMPLETEFSTATETRANSITION callback, DxgkCbCompleteFStateTransition, DxgkCbCompleteFStateTransition callback function [Display Devices], PDXGKCB_COMPLETEFSTATETRANSITION, d3dkmddi/DxgkCbCompleteFStateTransition, display.dxgkcbcompletefstatetransition
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8 (WDDM 1.2)
req.target-min-winversvr: Windows Server 2012
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_COMPLETEFSTATETRANSITION
 - d3dkmddi/DXGKCB_COMPLETEFSTATETRANSITION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DXGKCB_COMPLETEFSTATETRANSITION
---

# DXGKCB_COMPLETEFSTATETRANSITION callback function

## -description

**DXGKCB_COMPLETEFSTATETRANSITION** notifies the port driver that a power component has completed the F-state transition.

## -parameters

### -param hAdapter

[in] A handle to the display adapter. The display miniport driver receives the handle from the **DeviceHandle** member of the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md) structure in a call to its [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -param ComponentIndex

[in] The power component index specified by  [**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md).**pInputData** in a call to the [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function.

## -remarks

During component registration the display miniport driver should indicate all power components for which it will need to call the **DXGKCB_COMPLETEFSTATETRANSITION** function by setting the [**DXGK_POWER_COMPONENT_FLAGS**](ns-d3dkmddi-_dxgk_power_component_flags.md).**DriverCompletesFStateTransition** member to 1. When this member is set, the driver must call this function either synchronously or asynchronously. Conversely, if this member is not set, the driver should not call this function.

> [!NOTE]
>
> If [**DXGK_POWER_COMPONENT_FLAGS**](ns-d3dkmddi-_dxgk_power_component_flags.md).**DriverCompletesFStateTransition** has been set but the driver does not call this function, deadlocks might occur.

The Windows power management framework guarantees that no new transition request will be sent for the component until this function is called.

Usually the port driver expects that when this function returns, the F-state transition is completed. There could be scenarios when the display miniport driver cannot complete the transition synchronously, for example if the display miniport driver cannot complete the transitions at **DISPATCH_LEVEL**, or it needs to activate other power components. This function helps the display miniport driver to complete the F-state transition asynchronously.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_ALLOCATEPAGESFORMDL**](ns-d3dkmddi-_dxgkargcb_allocatepagesformdl.md) and then call **DxgkCbCompleteFStateTransition** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGK_POWER_COMPONENT_FLAGS**](ns-d3dkmddi-_dxgk_power_component_flags.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
