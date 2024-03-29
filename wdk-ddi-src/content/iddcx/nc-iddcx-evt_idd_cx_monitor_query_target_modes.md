---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES
title: EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES (iddcx.h)
description: Learn more about the EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES callback function.
tech.root: display
ms.date: 09/22/2023
keywords: ["EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES callback function"]
ms.keywords: EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES, EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES callback, EvtIddCxMonitorQueryTargetModes, EvtIddCxMonitorQueryTargetModes callback function [Display Devices], PFN_IDD_CX_MONITOR_QUERY_TARGET_MODES, PFN_IDD_CX_MONITOR_QUERY_TARGET_MODES callback function pointer [Display Devices], display.evt_idd_cx_monitor_query_target_modes, iddcx/EvtIddCxMonitorQueryTargetModes
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
req.irql:
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES
 - iddcx/EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES
---

# EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES callback function

## -description

**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES** is called by the OS to get a list of target modes supported by the driver for a monitor connected to the endpoint. Use [**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES2**](nc-iddcx-evt_idd_cx_monitor_query_target_modes2.md) to report additional information for HDR10 and WCG target modes.

## -parameters

### -param MonitorObject

[in] The OS-generated context handle that identifies the monitor to generate a list of target modes for. This [IDDCX_MONITOR](/windows-hardware/drivers/display/iddcx-objects#iddcx_monitor) object was returned in a prior call to [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md).

### -param pInArgs

[in] Pointer to a [**IDARG_IN_QUERYTARGETMODES**](ns-iddcx-idarg_in_querytargetmodes.md) structure that contains input arguments used by **EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES**.

### -param pOutArgs

[out] Pointer to a [**IDARG_OUT_QUERYTARGETMODES**](ns-iddcx-idarg_out_querytargetmodes.md) structure that contains output arguments generated by **EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES**.

## -returns

**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES** returns an [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) value. If the operation is successful, it returns STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, it returns an appropriate NTSTATUS error code.

## -see-also

[**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES2**](nc-iddcx-evt_idd_cx_monitor_query_target_modes2.md)

[**IDARG_IN_QUERYTARGETMODES**](ns-iddcx-idarg_in_querytargetmodes.md)

[**IDARG_OUT_QUERYTARGETMODES**](ns-iddcx-idarg_out_querytargetmodes.md)
