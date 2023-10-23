---
UID: NF:iddcx.IddCxMonitorUpdateModes
title: IddCxMonitorUpdateModes function (iddcx.h)
description: Learn more about the IddCxMonitorUpdateModes function.
tech.root: display
ms.date: 09/22/2023
keywords: ["IddCxMonitorUpdateModes function"]
ms.keywords: IddCxMonitorUpdateModes, IddCxMonitorUpdateModes method [Display Devices], display.iddcxmonitorupdatemodes, iddcx/IddCxMonitorUpdateModes
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
req.irql: _Must_inspect_result_
targetos: Windows
req.typenames: 
f1_keywords:
 - IddCxMonitorUpdateModes
 - iddcx/IddCxMonitorUpdateModes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - IddCx.dll
api_name:
 - IddCxMonitorUpdateModes
---

# IddCxMonitorUpdateModes function

## -description

An indirect display driver calls **IddCxMonitorUpdateModes** to have the OS update the mode list for a monitor. A driver that reports HDR support must use [**IddCxMonitorUpdateModes2**](nf-iddcx-iddcxmonitorupdatemodes2.md) instead.

## -parameters

### -param MonitorObject

[in] An [**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects) object that is the OS's context handle for the monitor. The OS provided this handle in a prior call to [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md).

### -param pInArgs

[in] Pointer to an [**IDARG_IN_UPDATEMODES**](ns-iddcx-idarg_in_updatemodes.md) structure that contains the input arguments for this function.

## -returns

**IddCxMonitorUpdateModes** returns STATUS_SUCCESS upon success; otherwise it returns an [appropriate NTSTATUS error code](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

A driver can call **IddCxMonitorUpdateModes** to update the mode list previously reported for a monitor.

## -see-also

[**IDARG_IN_UPDATEMODES**](ns-iddcx-idarg_in_updatemodes.md)

[**IddCxMonitorUpdateModes2**](nf-iddcx-iddcxmonitorupdatemodes2.md)
