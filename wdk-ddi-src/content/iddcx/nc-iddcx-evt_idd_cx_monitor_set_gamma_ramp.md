---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP
title: EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP (iddcx.h)
description: EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP is called by the OS to set a gamma ramp on the specified monitor.
old-location: display\evt_idd_cx_monitor_set_gamma_ramp.htm
tech.root: display
ms.assetid: 3e0828ee-307a-48fd-a8ea-b469ac6214d0
ms.date: 05/10/2018
keywords: ["EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP callback function"]
ms.keywords: EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP, EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP callback, EvtIddCxMonitorSetGammaRamp, EvtIddCxMonitorSetGammaRamp callback function [Display Devices], PFN_IDD_CX_MONITOR_SET_GAMMA_RAMP, PFN_IDD_CX_MONITOR_SET_GAMMA_RAMP callback function pointer [Display Devices], display.evt_idd_cx_monitor_set_gamma_ramp, iddcx/EvtIddCxMonitorSetGammaRamp
f1_keywords:
 - "iddcx/PFN_IDD_CX_MONITOR_SET_GAMMA_RAMP"
 - "PFN_IDD_CX_MONITOR_SET_GAMMA_RAMP"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- iddcx.h
api_name:
- PFN_IDD_CX_MONITOR_SET_GAMMA_RAMP
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP callback function


## -description


<b>EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP</b> is called by the OS to set a gamma ramp on the specified monitor.


## -parameters




### -param MonitorObject [in]

A handle by the OS to identify the monitor to set a gamma ramp for.


### -param pInArgs [in]

Input arguments used by <b>EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP</b>.


## -returns




(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code. 
                    



