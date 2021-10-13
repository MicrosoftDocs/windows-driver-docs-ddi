---
UID: NC:d3dkmddi.DXGKCB_MULTIPLANEOVERLAYDISABLED
title: DXGKCB_MULTIPLANEOVERLAYDISABLED (d3dkmddi.h)
description: This callback allows the kernel mode driver to indicate that the current multiplane overlay configuration is no longer supported on the specified VidPnSourceId.
old-location: display\dxgkcb_multiplaneoverlaydisabled.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_MULTIPLANEOVERLAYDISABLED callback function"]
ms.keywords: DXGKCB_MULTIPLANEOVERLAYDISABLED, DXGKCB_MULTIPLANEOVERLAYDISABLED callback, DXGKCB_MULTIPLANEOVERLAYDISABLED callback function [Display Devices], d3dkmddi/DXGKCB_MULTIPLANEOVERLAYDISABLED, display.dxgkcb_multiplaneoverlaydisabled
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607 (WDDM 2.1)
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
req.irql: <= PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_MULTIPLANEOVERLAYDISABLED
 - d3dkmddi/DXGKCB_MULTIPLANEOVERLAYDISABLED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_MULTIPLANEOVERLAYDISABLED
product:
 - Windows
---

# DXGKCB_MULTIPLANEOVERLAYDISABLED callback function

## -description

A kernel-mode display miniport driver calls **DXGKCB_MULTIPLANEOVERLAYDISABLED** to indicate that the current multiplane overlay (MPO) configuration is no longer supported on the specified *VidPnSourceId*.

## -parameters

### -param hAdapter

[in] Handle to the adapter on which the current MPO hardware configuration is no longer supported.

### -param VidPnSourceId

[in] The *VidPnSourceId* on which the current MPO hardware configuration is no longer supported.

## -returns

**DXGKCB_MULTIPLANEOVERLAYDISABLED** returns STATUS_SUCCESS on successful completion; otherwise it returns an appropriate NTSTATUS error code.

## -remarks

**DXGKCB_MULTIPLANEOVERLAYDISABLED** notifies the Desktop Windows Manager (DWM) that the current MPO configuration is no longer supported, allowing the DWM to fall back to composition.

This request is processed asynchronously and can be delayed by several frames. It is recommended to call this function only in exceptional cases such as the following scenarios:

* A display change or hot plug event on one output makes it no longer possible to continue supporting an MPO configuration that is committed to a different monitor. In this case, the driver can disable the overlay planes on the monitor. The user will see a visible artifact but it should be corrected eventually by the DWM.

* MPO should be disabled due to thermal issues. In this case, the driver does not need to immediately disable MPO, but can wait until the DWM receives the notification and requires MPO support (which the KMD should indicate is not supported due to the thermal issue). At that time, the DWM will disable MPO and start composing.

 For typical cases, drivers should instead prevent incompatible multiplane overlay configurations by responding correctly to [DxgkDdiCheckMultiplaneOverlaySupport3](nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport3.md).

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, call **DxgkCbMultiPlaneOverlayDisabled** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[DxgkDdiCheckMultiplaneOverlaySupport3](nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport3.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
