---
UID: NF:iddcx.IddCxMonitorQueryHardwareCursor
title: IddCxMonitorQueryHardwareCursor function (iddcx.h)
description: An OS callback function the driver calls when it wants obtain the updated cursor information. The driver normally only calls this when the event that signals cursor update has triggered.
old-location: display\iddcxmonitorqueryhardwarecursor.htm
tech.root: display
ms.date: 08/05/2022
keywords: ["IddCxMonitorQueryHardwareCursor function"]
ms.keywords: IddCxMonitorQueryHardwareCursor, IddCxMonitorQueryHardwareCursor method [Display Devices], display.iddcxmonitorqueryhardwarecursor, iddcx/IddCxMonitorQueryHardwareCursor
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
req.lib: IddCxStub.lib
req.dll: IddCx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IddCxMonitorQueryHardwareCursor
 - iddcx/IddCxMonitorQueryHardwareCursor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - IddCx.dll
api_name:
 - IddCxMonitorQueryHardwareCursor
---

# IddCxMonitorQueryHardwareCursor function

## -description

An indirect display driver calls **IddCxMonitorQueryHardwareCursor** to obtain updated hardware cursor information for the specified monitor.

## -parameters

### -param MonitorObject [in]

An [**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects) object which is the monitor's OS context handle created by [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md).

### -param pInArgs [in]

An [**IDARG_IN_QUERY_HWCURSOR**](ns-iddcx-idarg_in_query_hwcursor.md) structure containing this function's input arguments.

### -param pOutArgs [out]

An [**IDARG_OUT_QUERY_HWCURSOR**](ns-iddcx-idarg_out_query_hwcursor.md) structure in which the monitor's current hardware cursor information is returned.

## -returns

**IddCxMonitorQueryHardwareCursor** returns STATUS_SUCCESS if the operation succeeds; otherwise, it returns an [appropriate NTSTATUS error code](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

The driver normally only calls this function when [the event that signals cursor update](ns-iddcx-idarg_in_setup_hwcursor.md) has triggered.

For additional cursor information beyond what this function returns, call [**IddCxMonitorQueryHardwareCursor2**](nf-iddcx-iddcxmonitorqueryhardwarecursor2.md).

## -see-also

[**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects)

[**IDARG_IN_QUERY_HWCURSOR**](ns-iddcx-idarg_in_query_hwcursor.md)

[**IDARG_OUT_QUERY_HWCURSOR**](ns-iddcx-idarg_out_query_hwcursor.md)

[**IddCxMonitorQueryHardwareCursor2**](nf-iddcx-iddcxmonitorqueryhardwarecursor2.md)

[**IddCxMonitorSetupHardwareCursor**](nf-iddcx-iddcxmonitorsetuphardwarecursor.md)
