---
UID: NF:iddcx.IddCxMonitorUpdateModes2
tech.root: display
title: IddCxMonitorUpdateModes2
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IddCxMonitorUpdateModes2 function.
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
 - IddCxMonitorUpdateModes2
f1_keywords:
 - IddCxMonitorUpdateModes2
 - iddcx/IddCxMonitorUpdateModes2
dev_langs:
 - c++
helpviewer_keywords:
 - IddCxMonitorUpdateModes2
---

## -description

An indirect display driver calls **IddCxMonitorUpdateModes2** to have the OS update the mode list for a monitor.

## -parameters

### -param MonitorObject

[in] An [**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects) object that is the OS's context handle for the monitor. The OS provided this handle in a prior call to [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md).

### -param pInArgs

[in] Pointer to an [**IDARG_IN_UPDATEMODES2**](ns-iddcx-idarg_in_updatemodes2.md) structure that contains the input arguments for this function.

## -returns

**IddCxMonitorUpdateModes2** returns STATUS_SUCCESS upon success; otherwise it returns an [appropriate NTSTATUS error code](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

A driver can call **IddCxMonitorUpdateModes2** to update the mode list previously reported for a monitor.

Drivers sending modes with SDR WCG or HDR parameters will fail if they have not also reported [**IDDCX_ADAPTER_FLAGS_CAN_PROCESS_FP16**](ne-iddcx-iddcx_adapter_flags.md) in the [**IddCxAdapterInitAsync**](nf-iddcx-iddcxadapterinitasync.md) call. Also, drivers reporting **IDDCX_ADAPTER_FLAGS_CAN_PROCESS_FP16** can only call **IddCxMonitorUpdateModes2**; calling **IddCxMonitorUpdateModes** is an error.

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_IN_UPDATEMODES2**](ns-iddcx-idarg_in_updatemodes2.md)
