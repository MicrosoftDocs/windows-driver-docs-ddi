---
UID: NS:d3dkmddi._DXGKARG_QUERYADAPTERINFO
title: DXGKARG_QUERYADAPTERINFO (d3dkmddi.h)
description: Learn more about the DXGKARG_QUERYADAPTERINFO structure.
ms.date: 08/19/2024
keywords: ["DXGKARG_QUERYADAPTERINFO structure"]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.irql:
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
 - _DXGKARG_QUERYADAPTERINFO
 - DXGKARG_QUERYADAPTERINFO
---

# DXGKARG_QUERYADAPTERINFO structure

## -description

The **DXGKARG_QUERYADAPTERINFO** structure contains parameters for a [**DXGKDDI_QUERYADAPTERINFO**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) query.

## -struct-fields

### -field Type [in]

A [**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md)-typed value that indicates the type of information to retrieve. This value determines what **pInputData** and **pOutputData** point to.

### -field pInputData [in]

A pointer to input information for the query. The following table describes the input buffer for **Type** values requiring input. Other types don't require input, so **pInputData** is NULL.

| Value of **Type** | Contents of **pInputData** |
| --- | --- |
| DXGKQAITYPE_UMDRIVERPRIVATE | A proprietary buffer that contains information about the query. |
| DXGKQAITYPE_QUERYSEGMENT | A [**DXGK_QUERYSEGMENTIN**](ns-d3dkmddi-_dxgk_querysegmentin.md) structure. |
| DXGKQAITYPE_POWERCOMPONENTINFO | Buffer containing the power component index. |
| DXGKQAITYPE_DIRTYBITTRACKINGSEGMENTCAPS | Buffer containing the driver's segment ID. The driver should fill out the output caps for this particular segment. |
| DXGKQAITYPE_SCATTER_RESERVE | A [**DXGK_QUERYSCATTERRESERVEIN**](ns-d3dkmddi-dxgk_queryscatterreservein.md) structure. |
| DXGKQAITYPE_PAGINGPROCESSGPUVASIZE | A UNIT value that specifies the physical adapter index in an LDA configuration. It's set to zero for non-LDA configurations. |

### -field InputDataSize [in]

The size, in bytes, of the input data that **pInputData** points to.

### -field pOutputData [out]

A pointer to an output buffer that the display miniport driver fills with the required information. See [**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md) for the type of structure that **pOutputData** points to.

### -field OutputDataSize [in]

The size, in bytes, of the output data that **pOutputData** points to.

### -field Flags [in]

A set of [**DXGK_QUERYADAPTERINFOFLAGS**](ns-d3dkmddi-_dxgk_queryadapterinfoflags.md)-typed flags that indicates the query of graphics information.

### -field hKmdProcessHandle [in]

A handle, return by the KMD from DxgkDdiCreateProcess. The driver must check the value for NULL. Note that hKmdProcessHandle is created when the first DXG device is created for the adapter, and destroyed when the last adapter handle in the process is closed.

## -see-also

[**DXGK_DRIVERCAPS**](ns-d3dkmddi-_dxgk_drivercaps.md)

[**DXGK_QUERYADAPTERINFOFLAGS**](ns-d3dkmddi-_dxgk_queryadapterinfoflags.md)

[**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)
