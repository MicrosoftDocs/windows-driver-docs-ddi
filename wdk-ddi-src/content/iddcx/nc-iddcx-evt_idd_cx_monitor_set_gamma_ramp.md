---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP
title: EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP (iddcx.h)
description: EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP is called by the OS to set a gamma ramp on the specified monitor.
old-location: display\evt_idd_cx_monitor_set_gamma_ramp.htm
tech.root: display
ms.date: 08/08/2022
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

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.
