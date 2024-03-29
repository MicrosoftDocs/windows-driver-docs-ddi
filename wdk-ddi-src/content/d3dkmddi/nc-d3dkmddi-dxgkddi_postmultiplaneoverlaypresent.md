---
UID: NC:d3dkmddi.DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT
title: DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT (d3dkmddi.h)
description: Called after a new multi-plane overlay configuration has taken effect, allowing the driver to optimize hardware state. Optional for Windows Display Driver Model (WDDM) 2.0 or later drivers that support multi-plane overlays.
old-location: display\dxgkddi_postmultiplaneoverlaypresent.htm
ms.date: 04/16/2018
keywords: ["DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT callback function"]
ms.keywords: DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT, DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT callback, DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT callback function [Display Devices], d3dkmddi/DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT, display.dxgkddi_postmultiplaneoverlaypresent
req.header: d3dkmddi.h
req.include-header: 
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
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT
 - d3dkmddi/DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT
---

# DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT callback function


## -description

Called after a new multi-plane overlay configuration has taken effect, allowing the driver to optimize hardware state.  Optional for Windows Display Driver Model (WDDM) 2.0 or later drivers that support multi-plane overlays.

## -parameters

### -param hAdapter

Identifies the adapter containing the overlay hardware.

### -param pPostPresent

A pointer to a [DXGKARG_POSTMULTIPLANEOVERLAYPRESENT](ns-d3dkmddi-_dxgkarg_postmultiplaneoverlaypresent.md) structure that describes the new overlay configuration recently committed.

## -returns

**DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT** returns the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|If the routine has been successfully completed. The driver should always return a success code.  Failures will result in a bugcheck.|

## -remarks

This function is called from PASSIVE level.

This function is only called when driver sets PostPresentNeeded of [DXGKCB_NOTIFY_MPO_VSYNC_FLAGS](ns-d3dkmddi-_dxgkcb_notify_mpo_vsync_flags.md) member of the [DXGKARGCB_NOTIFY_INTERRUPT_DATA](ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md) structure in the VSYNC callback.

The driver can use this function to lower voltage levels, clocks, FIFO depths, or any other optimization that can save power.

The driver should not spend significant amount of time in this call because the call blocks the main GPU scheduler thread and delay could lead to present glitches. Time intensive actions should be queued as separate work items by driver and handled in background. In this scenario, any conflicts between the queued item and hardware changes demanded by future pre/post calls should be managed by driver.

