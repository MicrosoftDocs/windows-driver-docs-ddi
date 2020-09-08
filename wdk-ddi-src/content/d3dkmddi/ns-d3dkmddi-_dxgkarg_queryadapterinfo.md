---
UID: NS:d3dkmddi._DXGKARG_QUERYADAPTERINFO
title: _DXGKARG_QUERYADAPTERINFO (d3dkmddi.h)
description: The DXGKARG_QUERYADAPTERINFO structure contains parameters for a query.
old-location: display\dxgkarg_queryadapterinfo.htm
ms.assetid: 5992c846-93de-4f95-839a-81f14db709f7
ms.date: 05/10/2018
keywords: ["DXGKARG_QUERYADAPTERINFO structure"]
ms.keywords: DXGKARG_QUERYADAPTERINFO, DXGKARG_QUERYADAPTERINFO structure [Display Devices], DmStructs_82a38a66-d65c-4b88-be6d-974590e9472a.xml, _DXGKARG_QUERYADAPTERINFO, d3dkmddi/DXGKARG_QUERYADAPTERINFO, display.dxgkarg_queryadapterinfo
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.typenames: DXGKARG_QUERYADAPTERINFO
f1_keywords:
 - _DXGKARG_QUERYADAPTERINFO
 - d3dkmddi/_DXGKARG_QUERYADAPTERINFO
 - DXGKARG_QUERYADAPTERINFO
 - d3dkmddi/DXGKARG_QUERYADAPTERINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKARG_QUERYADAPTERINFO
---

# _DXGKARG_QUERYADAPTERINFO structure


## -description

The DXGKARG_QUERYADAPTERINFO structure contains parameters for a query.

## -struct-fields

### -field Type

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_queryadapterinfotype">DXGK_QUERYADAPTERINFOTYPE</a>-typed value that indicates the type of information to retrieve.

### -field pInputData

[in] A pointer to input information for the query.

When <b>Type</b> specifies DXGKQAITYPE_UMDRIVERPRIVATE, <b>pInputData</b> points to a proprietary buffer that contains information about the query. When <b>Type</b> specifies DXGKQAITYPE_QUERYSEGMENT, <b>pInputData</b> points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentin">DXGK_QUERYSEGMENTIN</a> structure. When <b>Type</b> specifies <b>DXGKQAITYPE_POWERCOMPONENTINFO</b>, <b>pInputData</b> points to an input buffer that contains the power component index.

An input buffer is not required when <b>Type</b> specifies the DXGKQAITYPE_DRIVERCAPS value.

### -field InputDataSize

[in] The size, in bytes, of the input data that <b>pInputData</b> points to.

### -field pOutputData

[out] A pointer to an output buffer that the display miniport driver fills with the required information.

| **Value of Type** | **Contents of output buffer pointed to by pOutputData** |
|:--|:--|
| **DXGKQAITYPE_UMDRIVERPRIVATE** | Proprietary buffer |
| **DXGKQAITYPE_DRIVERCAPS** | Populated [DXGK_DRIVERCAPS](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps) structure | 
| **DXGKQAITYPE_QUERYSEGMENT** | Populated [DXGK_QUERYSEGMENTOUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentout) structure | 
| **DXGKQAITYPE_QUERYSEGMENT3** | Populated [DXGK_QUERYSEGMENTOUT3](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentout3)  structure |
| **DXGKQAITYPE_NUMPOWERCOMPONENTS** | A UINT value that specifies the number of power components used by the display miniport driver. |
| **DXGKQAITYPE_POWERCOMPONENTINFO** | Populated [DXGK_POWER_RUNTIME_COMPONENT](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_power_runtime_component) structure that provides information about the nth power component, where n is the component index specified by pInputData in a call to the [DxgkDdiQueryAdapterInfo](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo)  function. |

### -field OutputDataSize

[in] The size, in bytes, of the output data that <b>pOutputData</b> points to.

### -field Flags

[in] A set of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_queryadapterinfoflags.md">DXGK_QUERYADAPTERINFOFLAGS</a>-typed flags that indicates the query of graphics information.

### -field hKmdProcessHandle

[in] A handle, return by the KMD from DxgkDdiCreateProcess. The driver must check the value for NULL. Note that hKmdProcessHandle is created when the first DXG device is created for the adapter, and destroyed when the last adapter handle in the process is closed.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxgk-power-p-component">DXGK_POWER_P_COMPONENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_power_runtime_component">DXGK_POWER_RUNTIME_COMPONENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_queryadapterinfotype">DXGK_QUERYADAPTERINFOTYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentin">DXGK_QUERYSEGMENTIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentout">DXGK_QUERYSEGMENTOUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentout3">DXGK_QUERYSEGMENTOUT3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>

