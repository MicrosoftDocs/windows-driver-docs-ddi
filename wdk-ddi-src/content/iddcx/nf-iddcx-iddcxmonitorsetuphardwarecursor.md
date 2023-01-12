---
UID: NF:iddcx.IddCxMonitorSetupHardwareCursor
title: IddCxMonitorSetupHardwareCursor function (iddcx.h)
description: An OS callback function the driver calls when it wants to setup hardware cursor support for the path.
old-location: display\iddcxmonitorsetuphardwarecursor.htm
tech.root: display
ms.date: 08/05/2022
keywords: ["IddCxMonitorSetupHardwareCursor function"]
ms.keywords: IddCxMonitorSetupHardwareCursor, IddCxMonitorSetupHardwareCursor method [Display Devices], display.iddcxmonitorsetuphardwarecursor, iddcx/IddCxMonitorSetupHardwareCursor
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
 - IddCxMonitorSetupHardwareCursor
 - iddcx/IddCxMonitorSetupHardwareCursor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - IddCx.dll
api_name:
 - IddCxMonitorSetupHardwareCursor
---

# IddCxMonitorSetupHardwareCursor function

## -description

An indirect display driver calls **IddCxMonitorSetupHardwareCursor** to setup hardware cursor support for the path.

## -parameters

### -param MonitorObject [in]

An [**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects) object which is the monitor's OS context handle created by [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md).

### -param pInArgs [in]

An [**IDARG_IN_SETUP_HWCURSOR**](ns-iddcx-idarg_in_setup_hwcursor.md) structure containing this function's input arguments.

## -returns

**IddCxMonitorSetupHardwareCursor** returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an [appropriate NTSTATUS error code](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

By default, software cursor is enabled when a mode is committed on a path. If the driver wants to accelerate the cursor on that path it uses this callback to enable hardware cursor support.

## -see-also

[**IDARG_IN_SETUP_HWCURSOR**](ns-iddcx-idarg_in_setup_hwcursor.md)

[**IddCxMonitorQueryHardwareCursor**](nf-iddcx-iddcxmonitorqueryhardwarecursor.md)

[**IddCxMonitorQueryHardwareCursor2**](nf-iddcx-iddcxmonitorqueryhardwarecursor2.md)
