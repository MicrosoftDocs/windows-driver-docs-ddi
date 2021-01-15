---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT
title: EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT (iddcx.h)
description: EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT is called by the OS to create an OPM protected output context.
old-location: display\evt_idd_cx_monitor_opm_create_protected_output.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT callback function"]
ms.keywords: EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT, EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT callback, EvtIddCxMonitorOpmCreateProtectedOutput, EvtIddCxMonitorOpmCreateProtectedOutput callback function [Display Devices], PFN_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT, PFN_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT callback function pointer [Display Devices], display.evt_idd_cx_monitor_opm_create_protected_output, iddcx/EvtIddCxMonitorOpmCreateProtectedOutput
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
 - EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT
 - iddcx/EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT
---

# EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT callback function


## -description

**EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT** is called by the OS to create an OPM protected output context.

## -parameters

### -param MonitorObject

[in] A handle used by the OS to identify the monitor that the OPM context should be created on.

### -param OpmCxtObject

[in] A context used by the OS to identify the OPM context the call is for.

### -param pInArgs

[in] Input arguments used by **EVT_IDD_CX_MONITOR_OPM CREATE_PROTECTED_OUTPUT**.

## -returns

(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

