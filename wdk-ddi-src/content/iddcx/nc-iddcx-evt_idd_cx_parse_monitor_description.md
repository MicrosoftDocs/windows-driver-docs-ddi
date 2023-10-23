---
UID: NC:iddcx.EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION
title: EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION (iddcx.h)
description: Learn more about the EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION callback function.
old-location: display\evt_idd_cx_parse_monitor_description.htm
tech.root: display
ms.date: 09/22/2023
keywords: ["EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION callback function"]
ms.keywords: EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION, EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION callback, EvtIddCxParseMonitorDescription, EvtIddCxParseMonitorDescription callback function [Display Devices], PFN_IDD_CX_PARSE_MONITOR_DESCRIPTION, PFN_IDD_CX_PARSE_MONITOR_DESCRIPTION callback function pointer [Display Devices], display.evt_idd_cx_parse_monitor_description, iddcx/EvtIddCxParseMonitorDescription
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
 - EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION
 - iddcx/EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION
---

# EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION callback function

## -description

The OS calls **EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION** to ask the driver to parse a monitor description into a list of modes that the monitor supports. Use [**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2**](nc-iddcx-evt_idd_cx_parse_monitor_description2.md) to report HDR10 or WCG monitor modes.

## -parameters

### -param pInArgs

[in] Pointer to a [**IDARG_IN_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_in_parsemonitordescription.md) structure that contains the input arguments for this callback function.

### -param pOutArgs

[out] Pointer to a [**IDARG_OUT_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_out_parsemonitordescription.md) structure that contains the output arguments for this callback function.

## -returns

**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION** returns an [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) value. If the operation is successful, it returns STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, it returns an appropriate NTSTATUS error code.

## -see-also

[**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2**](nc-iddcx-evt_idd_cx_parse_monitor_description2.md)

[**IDARG_IN_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_in_parsemonitordescription.md)

[**IDARG_OUT_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_out_parsemonitordescription.md)
