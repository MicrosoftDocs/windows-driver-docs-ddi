---
UID: NC:d3dkmddi.DXGKDDI_GETNODEMETADATA
title: DXGKDDI_GETNODEMETADATA (d3dkmddi.h)
description: From a provided adapter handle, returns the engine type and friendly name of an engine on a specified GPU node. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later display miniport drivers.
old-location: display\dxgkddigetnodemetadata.htm
ms.assetid: ECE54E1C-5291-43AF-8A71-BD95DE5DF0A6
ms.date: 05/10/2018
keywords: ["DXGKDDI_GETNODEMETADATA callback function"]
ms.keywords: DXGKDDI_GETNODEMETADATA, DXGKDDI_GETNODEMETADATA callback, DxgkDdiGetNodeMetadata, DxgkDdiGetNodeMetadata callback function [Display Devices], d3dkmddi/DxgkDdiGetNodeMetadata, display.dxgkddigetnodemetadata
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
 - "d3dkmddi/DxgkDdiGetNodeMetadata"
 - "DxgkDdiGetNodeMetadata"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DxgkDdiGetNodeMetadata
product:
 - Windows
---

# DXGKDDI_GETNODEMETADATA callback function

## -description

From a provided adapter handle, returns the engine type and friendly name of an engine on a specified GPU node. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later display miniport drivers.

## -parameters

### -param hAdapter

[in] A handle that identifies a display adapter. The DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.

### -param NodeOrdinalAndAdapterIndex

An index of a node for which engine information will be obtained. This node is within the physical adapter defined by the <i>hAdapter</i> parameter.

### -param pGetNodeMetadata

A pointer to a DXGKARG_GETNODEMETADATA structure that contains the engine type and friendly name of the engine specified by the <i>NodeOrdinal</i> parameter.

Note that the DXGKARG_GETNODEMETADATA structure is declared as a [DXGK_NODEMETADATA](../d3dkmdt/ns-d3dkmdt-_dxgk_nodemetadata.md) structure.

## -returns

Returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | [DxgkDdiGetNodeMetadata](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_getnodemetadata)  successfully retrieved the engine information. | 
| **STATUS_INVALID_PARAMETER** | The caller-provided hAdapter or pGetNodeMetadata parameters are invalid, or the caller-provided value of NodeOrdinal is greater than or equal to the number of nodes on the adapter. |

 

If the <i>hAdapter</i> and <i>pGetNodeMetadata</i> parameters are valid, and <i>NodeOrdinal</i> has a value in the range of 0 to (number of nodes - 1), all calls to this function must be successful.

## -remarks

For more information on how to implement this function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/enumerating-gpu-nodes">Enumerating GPU engine capabilities</a>.

## -see-also

[DXGK_NODEMETADATA](../d3dkmdt/ns-d3dkmdt-_dxgk_nodemetadata.md)

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>

