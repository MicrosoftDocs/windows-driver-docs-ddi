---
UID: NC:d3dkmddi.DXGKDDI_CREATEPROCESS
title: DXGKDDI_CREATEPROCESS (d3dkmddi.h)
description: DxgkDdiCreateProcess creates a graphics kernel process object.
old-location: display\dxgkddicreateprocess.htm
ms.assetid: E5AAEEB1-C29E-4AA7-9F8E-2C2DCFADED81
ms.date: 05/10/2018
ms.keywords: DXGKDDI_CREATEPROCESS, DXGKDDI_CREATEPROCESS callback, DxgkDdiCreateProcess, DxgkDdiCreateProcess callback function [Display Devices], d3dkmddi/DxgkDdiCreateProcess, display.dxgkddicreateprocess, dispmprt/DxgkDdiCreateProcess
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkDdiCreateProcess"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
 - d3dkmddi.h
api_name:
 - DxgkDdiCreateProcess
product:
 - Windows
---

# DXGKDDI_CREATEPROCESS callback function

## -description

<b>DxgkDdiCreateProcess</b> creates a graphics kernel process object.

## -parameters

### -param hAdapter

A handle to the display adapter.

### -param pArgs

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createprocess">DXGKARG_CREATEPROCESS</a> structure that describes the operation.

## -returns

      Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in <b>Ntstatus.h</b>.

## -remarks

During process creation the kernel mode driver is allowed to call the <b>DxgkCbReserveVirtualAddressRange</b> callback. At this point the graphics processing unit (GPU) virtual address space for the process is free and the driver has the opportunity to reserve virtual address space for its needs.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createprocess">DXGKARG_CREATEPROCESS</a>

