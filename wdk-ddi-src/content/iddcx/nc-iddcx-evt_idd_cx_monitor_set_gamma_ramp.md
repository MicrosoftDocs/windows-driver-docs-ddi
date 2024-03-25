---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP
title: EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP (iddcx.h)
description: Learn more about the EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP callback function.
tech.root: display
ms.date: 09/22/2023
keywords: ["EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP callback function"]
ms.keywords: EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP, EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP callback, EvtIddCxMonitorSetGammaRamp, EvtIddCxMonitorSetGammaRamp callback function [Display Devices], PFN_IDD_CX_MONITOR_SET_GAMMA_RAMP, PFN_IDD_CX_MONITOR_SET_GAMMA_RAMP callback function pointer [Display Devices], display.evt_idd_cx_monitor_set_gamma_ramp, iddcx/EvtIddCxMonitorSetGammaRamp
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.irql: _requires_same_
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP
 - iddcx/EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP
---

# EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP callback function

## -description

The operating system calls **EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP** to set a gamma ramp on the specified monitor.

## -parameters

### -param MonitorObject [in]

An [**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects) object which is the OS's context handle that identifies the monitor to set a gamma ramp for.

### -param pInArgs [in]

An [**IDARG_IN_SET_GAMMARAMP**](ns-iddcx-idarg_in_set_gammaramp.md) structure containing information about the gamma ramp being set.

## -returns

**EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP** returns an [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) value. If the operation is successful, it returns STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

If a driver reports [FP16 support](ns-iddcx-iddcx_adapter_caps.md) for an adapter it must also accept and use [**IDDCX_GAMMARAMP_TYPE_3x4_COLORSPACE_TRANSFORM**](ne-iddcx-iddcx_gammaramp_type.md) regardless of gamma support previously reported in a call to [**IddCxAdapterInitAsync**](nf-iddcx-iddcxadapterinitasync.md). This type of gamma ramp can be sent for any monitor even if HDR is not currently being used.

It's possible that some parts of the transform won't be required or have no effect. In this case, the OS will set the appropriate flag to FALSE allowing the driver to potentially use an optimized transform. Like other gamma ramps, the 3x4 transform must also be applied to mouse cursors.

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_IN_SET_GAMMARAMP**](ns-iddcx-idarg_in_set_gammaramp.md)

[**IDDCX_GAMMARAMP_TYPE_3x4_COLORSPACE_TRANSFORM**](ne-iddcx-iddcx_gammaramp_type.md)
