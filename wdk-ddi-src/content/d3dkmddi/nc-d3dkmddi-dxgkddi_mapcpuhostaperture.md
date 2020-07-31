---
UID: NC:d3dkmddi.DXGKDDI_MAPCPUHOSTAPERTURE
title: DXGKDDI_MAPCPUHOSTAPERTURE (d3dkmddi.h)
description: DxgkDdiMapCpuHostAperture is called to map an allocation that is resident in a local memory segment into the CPU host aperture in order to make it visible to the CPU.
old-location: display\dxgkddimapcpuhostaperture.htm
ms.assetid: 78729B9A-A9FA-4D1E-8D30-3FFD61B1A7D3
ms.date: 05/10/2018
keywords: ["DXGKDDI_MAPCPUHOSTAPERTURE callback function"]
ms.keywords: DXGKDDI_MAPCPUHOSTAPERTURE, DXGKDDI_MAPCPUHOSTAPERTURE callback, DxgkDdiMapCpuHostAperture, DxgkDdiMapCpuHostAperture callback function [Display Devices], d3dkmddi/DxgkDdiMapCpuHostAperture, display.dxgkddimapcpuhostaperture
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
 - "d3dkmddi/DxgkDdiMapCpuHostAperture"
 - "DxgkDdiMapCpuHostAperture"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiMapCpuHostAperture
product:
 - Windows
---

# DXGKDDI_MAPCPUHOSTAPERTURE callback function

## -description

<b>DxgkDdiMapCpuHostAperture</b> is called to map an allocation that is resident in a local memory segment into the CPU host aperture in order to make it visible to the CPU.

## -parameters

### -param hAdapter

A handle to the display adapter.

### -param pArgs

*Map* [in]

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_mapcpuhostaperture">DXGKARG_MAPCPUHOSTAPERTURE</a> structure that describes the operation.

## -returns

      Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in <b>Ntstatus.h</b>.

