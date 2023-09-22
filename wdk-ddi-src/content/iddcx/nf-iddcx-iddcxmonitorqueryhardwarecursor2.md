---
UID: NF:iddcx.IddCxMonitorQueryHardwareCursor2
tech.root: display
title: IddCxMonitorQueryHardwareCursor2
ms.date: 08/05/2022
targetos: Windows
description: Learn more about the IddCxMonitorQueryHardwareCursor2 function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IddCxMonitorQueryHardwareCursor2
f1_keywords:
 - IddCxMonitorQueryHardwareCursor2
 - iddcx/IddCxMonitorQueryHardwareCursor2
dev_langs:
 - c++
helpviewer_keywords:
 - IddCxMonitorQueryHardwareCursor2
---

## -description

An indirect display driver calls **IddCxMonitorQueryHardwareCursor2** to retrieve the current hardware cursor information for the specified monitor. A driver that reports HDR support must use [**IddCxMonitorQueryHardwareCursor3**](nf-iddcx-iddcxmonitorqueryhardwarecursor3.md) instead.

## -parameters

### -param MonitorObject

[in] An [**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects) object which is the monitor's OS context handle created by [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md).

### -param pInArgs

[in] Pointer to an [**IDARG_IN_QUERY_HWCURSOR**](ns-iddcx-idarg_in_query_hwcursor.md) structure containing this function's input arguments.

### -param pOutArgs

[out] Pointer to an [**IDARG_OUT_QUERY_HWCURSOR2**](ns-iddcx-idarg_out_query_hwcursor2.md) structure in which the monitor's current hardware cursor information is returned.

## -returns

**IddCxMonitorQueryHardwareCursor2** returns STATUS_SUCCESS upon success; otherwise it returns an [appropriate NTSTATUS error code](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

The driver normally only calls this function when the event that signals cursor update has triggered.

Although **IddCxMonitorQueryHardwareCursor2** can be used by both console and remote drivers, the additional information provided when compared to [**IddCxMonitorQueryHardwareCursor**](nf-iddcx-iddcxmonitorqueryhardwarecursor.md) is only useful for remote drivers.

## -see-also

[**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects)

[**IDARG_IN_QUERY_HWCURSOR**](ns-iddcx-idarg_in_query_hwcursor.md)

[**IDARG_OUT_QUERY_HWCURSOR2**](ns-iddcx-idarg_out_query_hwcursor2.md)

[**IddCxMonitorQueryHardwareCursor3**](nf-iddcx-iddcxmonitorqueryhardwarecursor3.md)

[**IddCxMonitorSetupHardwareCursor**](nf-iddcx-iddcxmonitorsetuphardwarecursor.md)
