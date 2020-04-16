---
UID: NC:d3dkmddi.DXGKDDI_QUERYENGINESTATUS
title: DXGKDDI_QUERYENGINESTATUS (d3dkmddi.h)
description: The display port driver's GPU scheduler calls this function to determine the progress of a node within an active physical display adapter (engine).
old-location: display\dxgkddiqueryenginestatus.htm
ms.assetid: 87c99fcb-d25a-41b1-a1f3-9cf9ab7b141e
ms.date: 05/10/2018
keywords: ["DXGKDDI_QUERYENGINESTATUS callback function"]
ms.keywords: DXGKDDI_QUERYENGINESTATUS, DXGKDDI_QUERYENGINESTATUS callback, DxgkDdiQueryEngineStatus, DxgkDdiQueryEngineStatus callback function [Display Devices], d3dkmddi/DxgkDdiQueryEngineStatus, display.dxgkddiqueryenginestatus
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - "d3dkmddi/DxgkDdiQueryEngineStatus"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DxgkDdiQueryEngineStatus
product:
 - Windows
---

# DXGKDDI_QUERYENGINESTATUS callback function

## -description

The display port driver's GPU scheduler calls this function to determine the progress of a node within an active physical display adapter (engine).

## -parameters

### -param hAdapter

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pQueryEngineStatus

A pointer to a   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryenginestatus">DXGKARG_QUERYENGINESTATUS</a> structure that specifies a node and physical adapter that are to be queried for progress, and that supplies a value for the progress.

## -returns

Returns STATUS_SUCCESS if the function succeeds. Otherwise, this function returns one of the error codes defined in Ntstatus.h.

## -remarks

 This function should be made pageable, and it should always succeed.

The operating system guarantees that this function follows the first level synchronization mode as defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-first-level">Threading and Synchronization First Level</a>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/tdr-changes-in-windows-8">TDR changes in Windows 8</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryenginestatus">DXGKARG_QUERYENGINESTATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>

