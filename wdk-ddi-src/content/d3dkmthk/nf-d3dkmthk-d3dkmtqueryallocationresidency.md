---
UID: NF:d3dkmthk.D3DKMTQueryAllocationResidency
title: D3DKMTQueryAllocationResidency function (d3dkmthk.h)
description: The D3DKMTQueryAllocationResidency function retrieves the residency status of a resource or list of allocations.
old-location: display\d3dkmtqueryallocationresidency.htm
ms.date: 02/28/2022
keywords: ["D3DKMTQueryAllocationResidency function"]
ms.keywords: D3DKMTQueryAllocationResidency, D3DKMTQueryAllocationResidency function [Display Devices], OpenGL_Functions_4efd6e87-91b6-4cf2-8691-0463a9ab218a.xml, d3dkmthk/D3DKMTQueryAllocationResidency, display.d3dkmtqueryallocationresidency
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTQueryAllocationResidency
 - d3dkmthk/D3DKMTQueryAllocationResidency
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - API-MS-Win-dx-d3dkmt-l1-1-0.dll
 - API-MS-Win-dx-d3dkmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTQueryAllocationResidency
---

# D3DKMTQueryAllocationResidency function

## -description

The **D3DKMTQueryAllocationResidency** function retrieves the residency status of a resource or list of allocations.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_QUERYALLOCATIONRESIDENCY](ns-d3dkmthk-_d3dkmt_queryallocationresidency.md) structure that contains information for retrieving the residency status of a resource or list of allocations.

## -returns

**D3DKMTQueryAllocationResidency** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | Residency status for allocations was successfully retrieved. |
| STATUS_DEVICE_REMOVED | The graphics adapter was stopped or the display device was reset. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -see-also

[D3DKMT_QUERYALLOCATIONRESIDENCY](ns-d3dkmthk-_d3dkmt_queryallocationresidency.md)
