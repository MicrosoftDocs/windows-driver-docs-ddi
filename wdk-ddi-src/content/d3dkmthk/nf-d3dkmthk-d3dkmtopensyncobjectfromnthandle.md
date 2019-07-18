---
UID: NF:d3dkmthk.D3DKMTOpenSyncObjectFromNtHandle
title: D3DKMTOpenSyncObjectFromNtHandle function (d3dkmthk.h)
description: Maps an NT process handle to a graphics processing unit (GPU) synchronization object.
old-location: display\d3dkmtopensyncobjectfromnthandle.htm
ms.assetid: 202695a2-cfe3-423f-b4da-a9ad312c5168
ms.date: 05/10/2018
ms.keywords: D3DKMTOpenSyncObjectFromNtHandle, D3DKMTOpenSyncObjectFromNtHandle function [Display Devices], d3dkmthk/D3DKMTOpenSyncObjectFromNtHandle, display.d3dkmtopensyncobjectfromnthandle
ms.topic: function
f1_keywords:
 - "d3dkmthk/D3DKMTOpenSyncObjectFromNtHandle"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- GDI32.dll
- API-MS-Win-dx-d3dkmt-l1-1-0.dll
- API-MS-Win-dx-d3dkmt-l1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTOpenSyncObjectFromNtHandle
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTOpenSyncObjectFromNtHandle function

## -description

Maps an NT process handle to a graphics processing unit (GPU) synchronization object.

## -parameters

### -param Arg1

*pObject* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_opensyncobjectfromnthandle">D3DKMT_OPENSYNCOBJECTFROMNTHANDLE</a> structure that describes information that is required to perform the mapping.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The mapping was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other NTSTATUS values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_opensyncobjectfromnthandle">D3DKMT_OPENSYNCOBJECTFROMNTHANDLE</a>
 

 

