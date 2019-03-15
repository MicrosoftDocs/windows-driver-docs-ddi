---
UID: NF:d3dkmthk.D3DKMTDestroyAllocation2
title: D3DKMTDestroyAllocation2 function (d3dkmthk.h)
description: The D3DKMTDestroyAllocation2 function releases a resource, a list of allocations, or both.
old-location: display\d3dkmtdestroyallocation2.htm
ms.assetid: C66CD2FB-AD45-4666-ACD4-6555ED681935
ms.date: 05/10/2018
ms.keywords: D3DKMTDestroyAllocation2, D3DKMTDestroyAllocation2 function [Display Devices], d3dkmthk/D3DKMTDestroyAllocation2, display.d3dkmtdestroyallocation2
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- API-MS-Win-DX-D3DKMT-L1-1-1.dll
- GDI32.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTDestroyAllocation2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTDestroyAllocation2 function

## -description

The <b>D3DKMTDestroyAllocation2</b> function releases a resource, a list of allocations, or both.


## -parameters

### -param D3DKMT_DESTROYALLOCATION2

*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906793">D3DKMT_DESTROYALLOCATION2</a> structure that contains information for releasing allocations.

## -returns

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546891">D3DKMTDestroyAllocation</a> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|Allocations were successfully released.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn906793">D3DKMT_DESTROYALLOCATION2</a>
