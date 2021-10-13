---
UID: NC:d3dkmddi.DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN
title: DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN (d3dkmddi.h)
description: DxgkCbHardwareContentProtectionTeardown is used to indicate when a hardware content protection event occurs.
old-location: display\dxgkcbhardwarecontentprotectionteardown.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN callback function"]
ms.keywords: DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN, DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN callback, DxgkCbHardwareContentProtectionTeardown, DxgkCbHardwareContentProtectionTeardown callback function [Display Devices], d3dkmddi/DxgkCbHardwareContentProtectionTeardown, display.dxgkcbhardwarecontentprotectionteardown
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
req.target-min-winversvr: Windows Server 2016
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN
 - d3dkmddi/DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN
---

# DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN callback function

## -description

**DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN** is called when a hardware content protection tear-down event occurs.

## -parameters

### -param hAdapter

[in] A handle to the graphics adapter where the tear-down event is occurring.

### -param Flags

[in] Additional flags defined by the [**DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS**](ne-d3dkmddi-_dxgk_hardware_content_protection_teardown_flags) enumeration.

## -remarks

The kernel-mode display miniport driver should always call **DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN** both before and after a hardware content protection tear-down event occurs.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, call **DxgkCbHardwareContentProtectionTeardown** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md). The driver can call this callback at either passive level or at dispatch level.

## -see-also

[**DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS**](ne-d3dkmddi-_dxgk_hardware_content_protection_teardown_flags)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
