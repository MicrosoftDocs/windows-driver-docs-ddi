---
UID: NF:d3dkmthk.D3DKMTDestroyPagingQueue
title: D3DKMTDestroyPagingQueue function (d3dkmthk.h)
description: D3DKMTDestroyPagingQueue waits for a paging queue to finish all operations queued to it, and destroys it along with the associated sync object.
old-location: display\d3dkmtdestroypagingqueue.htm
ms.assetid: 470563BD-F185-4CA2-B4AD-06E1AABD36AD
ms.date: 05/10/2018
keywords: ["D3DKMTDestroyPagingQueue function"]
ms.keywords: D3DKMTDestroyPagingQueue, D3DKMTDestroyPagingQueue function [Display Devices], d3dkmthk/D3DKMTDestroyPagingQueue, display.d3dkmtdestroypagingqueue
f1_keywords:
 - "d3dkmthk/D3DKMTDestroyPagingQueue"
 - "D3DKMTDestroyPagingQueue"
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
- D3DKMTDestroyPagingQueue
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTDestroyPagingQueue function

## -description

<b>D3DKMTDestroyPagingQueue</b> waits for a paging queue to finish all operations queued to it, and destroys it along with the associated sync object.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-d3dddi_destroypagingqueue">D3DDDI_DESTROYPAGINGQUEUE</a> structure that describes the operation.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The operation was performed successfully.|

This function might also return other <b>NTSTATUS</b> values.

## -remarks

In addition to <b>hPagingQueue</b>, this device driver interface (DDI) invalidates <b>hSyncObject</b> and <b>FenceValueCPUVirtualAddress</b> values returned from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatepagingqueue">D3DKMTCreatePagingQueue</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-d3dddi_destroypagingqueue">D3DDDI_DESTROYPAGINGQUEUE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatepagingqueue">D3DKMTCreatePagingQueue</a>
 

 

