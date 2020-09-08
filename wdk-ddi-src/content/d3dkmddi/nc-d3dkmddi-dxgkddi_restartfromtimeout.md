---
UID: NC:d3dkmddi.DXGKDDI_RESTARTFROMTIMEOUT
title: DXGKDDI_RESTARTFROMTIMEOUT (d3dkmddi.h)
description: The DxgkDdiRestartFromTimeout function indicates that the driver can access the graphics processing unit (GPU) again after the recovery from a hardware timeout has completed.
old-location: display\dxgkddirestartfromtimeout.htm
ms.assetid: 433babb7-9a53-4079-9a65-43a5ed0c201a
ms.date: 05/10/2018
keywords: ["DXGKDDI_RESTARTFROMTIMEOUT callback function"]
ms.keywords: DXGKDDI_RESTARTFROMTIMEOUT, DXGKDDI_RESTARTFROMTIMEOUT callback, DmFunctions_ba675ea3-7f25-446f-bf13-af2228aa1e65.xml, DxgkDdiRestartFromTimeout, DxgkDdiRestartFromTimeout callback function [Display Devices], d3dkmddi/DxgkDdiRestartFromTimeout, display.dxgkddirestartfromtimeout
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_RESTARTFROMTIMEOUT
 - d3dkmddi/DXGKDDI_RESTARTFROMTIMEOUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiRestartFromTimeout
product:
 - Windows
---

# DXGKDDI_RESTARTFROMTIMEOUT callback function


## -description

The <i>DxgkDdiRestartFromTimeout</i> function indicates that the driver can access the graphics processing unit (GPU) again after the recovery from a hardware timeout has completed.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

## -returns

<i>DxgkDdiRestartFromTimeout</i> returns STATUS_SUCCESS to indicate that the driver handled the call successfully; otherwise, the operating system bug checks and causes a restart.

## -remarks

The operating system calls the <i>DxgkDdiRestartFromTimeout</i> function after the recovery of a hardware tim-eout completes from the operating system's perspective (for example, all of the system-managed resources, mappings, and so on are released). The <i>DxgkDdiRestartFromTimeout</i> function indicates that the driver can begin to access the GPU and release any driver-managed resources. However, most drivers might not be required to perform any actions during a call to <i>DxgkDdiRestartFromTimeout</i>. Regardless of whether <i>DxgkDdiRestartFromTimeout</i> performs any actions, it must still be implemented and can simply return STATUS_SUCCESS immediately.

<i>DxgkDdiRestartFromTimeout</i> should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_resetfromtimeout">DxgkDdiResetFromTimeout</a>

