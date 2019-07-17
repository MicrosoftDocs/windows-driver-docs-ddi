---
UID: NF:d3dkmthk.D3DKMTQueryAllocationResidency
title: D3DKMTQueryAllocationResidency function (d3dkmthk.h)
description: The D3DKMTQueryAllocationResidency function retrieves the residency status of a resource or list of allocations.
old-location: display\d3dkmtqueryallocationresidency.htm
ms.assetid: f9522de0-54cd-4afd-b8cd-06f229ac1325
ms.date: 05/10/2018
ms.keywords: D3DKMTQueryAllocationResidency, D3DKMTQueryAllocationResidency function [Display Devices], OpenGL_Functions_4efd6e87-91b6-4cf2-8691-0463a9ab218a.xml, d3dkmthk/D3DKMTQueryAllocationResidency, display.d3dkmtqueryallocationresidency
ms.topic: function
f1_keywords:
 - "d3dkmthk/D3DKMTQueryAllocationResidency"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
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
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTQueryAllocationResidency function

## -description

The <b>D3DKMTQueryAllocationResidency</b> function retrieves the residency status of a resource or list of allocations.

## -parameters

### -param D3DKMT_QUERYALLOCATIONRESIDENCY

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryallocationresidency">D3DKMT_QUERYALLOCATIONRESIDENCY</a> structure that contains information for retrieving the residency status of a resource or list of allocations.

## -returns

<b>D3DKMTQueryAllocationResidency</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|Residency status for allocations was successfully retrieved.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display device was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other NTSTATUS values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryallocationresidency">D3DKMT_QUERYALLOCATIONRESIDENCY</a>
