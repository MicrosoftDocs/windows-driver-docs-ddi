---
UID: NF:iddcx.IddCxMonitorQueryHardwareCursor3
tech.root: display
title: IddCxMonitorQueryHardwareCursor3
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IddCxMonitorQueryHardwareCursor3 function.
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
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - iddcx.h
api_name:
 - IddCxMonitorQueryHardwareCursor3
f1_keywords:
 - IddCxMonitorQueryHardwareCursor3
 - iddcx/IddCxMonitorQueryHardwareCursor3
dev_langs:
 - c++
helpviewer_keywords:
 - IddCxMonitorQueryHardwareCursor3
---

## -description

An indirect display driver calls **IddCxMonitorQueryHardwareCursor3** to retrieve the current hardware cursor information for the specified monitor. This function version adds the SDR white level which a driver must apply to the cursor if the monitor is in an HDR mode.

## -parameters

### -param MonitorObject

[in] An [**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects) object which is the monitor's OS context handle created by [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md).

### -param pInArgs

Pointer to an [**IDARG_IN_QUERY_HWCURSOR**](ns-iddcx-idarg_in_query_hwcursor.md) structure containing this function's input arguments.

### -param pOutArgs

Pointer to an [**IDARG_OUT_QUERY_HWCURSOR3**](ns-iddcx-idarg_out_query_hwcursor3.md) structure in which the monitor's current hardware cursor information is returned.

## -returns

**IddCxMonitorQueryHardwareCursor2** returns STATUS_SUCCESS upon success; otherwise it returns an [appropriate NTSTATUS error code](/windows-hardware/drivers/kernel/ntstatus-values). An error code of STATUS_GRAPHICS_PATH_NOT_IN_TOPOLOGY is a transient error indicating that the **MonitorObject** is not currently in an active path.

## -remarks

**IddCxMonitorQueryHardwareCursor3** retrieves the current hardware cursor information for the specified monitor and places it into the caller-supplied buffer that **pOutArgs** points to. This function is very similar to [**IddCxMonitorQueryHardwareCursor2**](nf-iddcx-iddcxmonitorqueryhardwarecursor2.md), but additionally provides the SDR white level value. The SDR white level is required because all cursor images are in SDR format and the driver needs to ensure they are displayed at the correct brightness.

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects)

[**IDARG_IN_QUERY_HWCURSOR**](ns-iddcx-idarg_in_query_hwcursor.md)

[**IDARG_OUT_QUERY_HWCURSOR3**](ns-iddcx-idarg_out_query_hwcursor3.md)

[**IddCxMonitorSetupHardwareCursor**](nf-iddcx-iddcxmonitorsetuphardwarecursor.md)
