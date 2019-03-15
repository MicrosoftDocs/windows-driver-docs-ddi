---
UID: NS:d3dkmddi._DXGK_MODE_BEHAVIOR_FLAGS
title: _DXGK_MODE_BEHAVIOR_FLAGS (d3dkmddi.h)
description: The high-level mode and setting behaviors which the OS may request.
ms.assetid: 309de6f3-d699-475b-a667-9d16cdf779d9
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _DXGK_MODE_BEHAVIOR_FLAGS, DXGK_MODE_BEHAVIOR_FLAGS,
req.header: d3dkmddi.h
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
req.typenames: DXGK_MODE_BEHAVIOR_FLAGS
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- _DXGK_MODE_BEHAVIOR_FLAGS
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGK_MODE_BEHAVIOR_FLAGS structure

## -description

The high-level mode and setting behaviors which the OS may request. The same union is used in different fields to describe the input request to the driver and the results output from the driver.

## -union-fields

| Member | Description |
| --- | --- |
| PrioritizeHDR | [in] If set, the driver should prioritize HDR support when enumerating display modes and setting display modes over other constraints such as balancing modes available on different targets, supporting high frequencies or high resolutions.  If not set, the driver should use its default policies for prioritizing the modes made available to the OS. |
| ColorimetricControl | Controls known color enhancements that affect the color accuracy of the display that the OS is not aware of. A value of one for Request.ColorimetricControl indicates that the OS is requesting the driver to disable any color enhancements that affect the color accuracy of the display. A zero value of Request.ColorimetricControl indicates the OS is informing the driver it is free to enable the any color enhancements that it had disabled. |
| Reserved | Reserved. |


### -field PrioritizeHDR

Prioritize HDR.

### -field ColorimetricControl

Controls known color enhancements that affect the color accuracy of the display that the OS is not aware of. A value of one for Request.ColorimetricControl indicates that the OS is requesting the driver to disable any color enhancements that affect the color accuracy of the display. A zero value of Request.ColorimetricControl indicates the OS is informing the driver it is free to enable the any color enhancements that it had disabled.

### -field Reserved

Reserved.

### -field Value


## -remarks

The following table describes how the driver should set the value of ColorimetricControl in the Satisfied and NotSatisfied member of the [DXGKARG_CONTROLMODEBEHAVIOR](ns-d3dkmddi-_dxgkarg_controlmodebehavior.md) structure.

|| Satisfied.ColorimetricControl | NotSatisfied.ColorimetricControl |
|:-- | -- | -- |
| Driver supports controlling the color enhancements and successfully changed the state requested in Request.ColorimetricControl | 1| 0|
| Driver supports controlling the color enhancements but was unsuccessful in changing the state requested in Request.ColorimetricControl| 0| 1|
| Driver does not support controlling the color enhancment| 0| 0|



