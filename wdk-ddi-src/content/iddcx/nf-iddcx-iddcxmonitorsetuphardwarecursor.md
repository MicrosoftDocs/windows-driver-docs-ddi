---
UID: NF:iddcx.IddCxMonitorSetupHardwareCursor
title: IddCxMonitorSetupHardwareCursor function (iddcx.h)
description: An OS callback function the driver calls when it wants to setup hardware cursor support for the path.
old-location: display\iddcxmonitorsetuphardwarecursor.htm
tech.root: display
ms.assetid: 6182898d-d7c0-4ff2-b222-d83bd00cd1ec
ms.date: 05/10/2018
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
req.irql: _Must_inspect_result_
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

                An OS callback function the driver calls when it wants to setup hardware cursor support for the path.  By default when a mode is committed on a path software cursor is enabled, if the driver wants to accelerate the cursor on that path it uses this callback to enable hardware cursor support.

## -parameters

### -param MonitorObject 

[in]
The handle the OS provided to identify the monitor

### -param pInArgs 

[in]
Input arguments of function

## -returns

(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.