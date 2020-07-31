---
UID: NF:d3dkmthk.D3DKMTOpenSyncObjectNtHandleFromName
title: D3DKMTOpenSyncObjectNtHandleFromName function (d3dkmthk.h)
description: D3DKMTOpenSyncObjectNtHandleFromName opens an NT handle for a named shared monitored fence object, similar to what D3DKMTOpenNtHandleFromName does for shared allocations.
old-location: display\d3dkmtopensyncobjectnthandlefromname.htm
ms.assetid: 29EF6C90-E25F-4E03-8834-EC2546B670AA
ms.date: 05/10/2018
keywords: ["D3DKMTOpenSyncObjectNtHandleFromName function"]
ms.keywords: D3DKMTOpenSyncObjectNtHandleFromName, D3DKMTOpenSyncObjectNtHandleFromName function [Display Devices], d3dkmthk/D3DKMTOpenSyncObjectNtHandleFromName, display.d3dkmtopensyncobjectnthandlefromname
f1_keywords:
 - "d3dkmthk/D3DKMTOpenSyncObjectNtHandleFromName"
 - "D3DKMTOpenSyncObjectNtHandleFromName"
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
- GDI32.dll
- API-MS-Win-DX-D3DKMT-L1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTOpenSyncObjectNtHandleFromName
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTOpenSyncObjectNtHandleFromName function

## -description

<b>D3DKMTOpenSyncObjectNtHandleFromName</b> opens an NT handle for a named shared monitored fence object, similar to what <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopennthandlefromname">D3DKMTOpenNtHandleFromName</a> does for shared allocations.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_opensyncobjectnthandlefromname">D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME</a> structure that describes the operation.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The operation was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopennthandlefromname">D3DKMTOpenNtHandleFromName</a>
