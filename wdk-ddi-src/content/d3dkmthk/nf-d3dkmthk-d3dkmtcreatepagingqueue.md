---
UID: NF:d3dkmthk.D3DKMTCreatePagingQueue
title: D3DKMTCreatePagingQueue function (d3dkmthk.h)
description: D3DKMTCreatePagingQueue is used to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.
old-location: display\d3dkmtcreatepagingqueue.htm
ms.assetid: B95ADBC5-35CC-486D-A5C7-0950ABF4B70A
ms.date: 05/10/2018
keywords: ["D3DKMTCreatePagingQueue function"]
ms.keywords: D3DKMTCreatePagingQueue, D3DKMTCreatePagingQueue function [Display Devices], d3dkmthk/D3DKMTCreatePagingQueue, display.d3dkmtcreatepagingqueue
f1_keywords:
 - "d3dkmthk/D3DKMTCreatePagingQueue"
 - "D3DKMTCreatePagingQueue"
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
- D3DKMTCreatePagingQueue
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTCreatePagingQueue function

## -description

<b>D3DKMTCreatePagingQueue</b> is used to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createpagingqueue">D3DKMT_CREATEPAGINGQUEUE</a> structure that describes the operation.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The operation was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createpagingqueue">D3DKMT_CREATEPAGINGQUEUE</a>
 

 

