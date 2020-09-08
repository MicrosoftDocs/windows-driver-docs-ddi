---
UID: NS:d3dukmdt.D3DDDI_DESTROYPAGINGQUEUE
title: D3DDDI_DESTROYPAGINGQUEUE (d3dukmdt.h)
description: D3DDDI_DESTROYPAGINGQUEUE is used with pfnDestroyPagingQueueCb and D3DKMTDestroyPagingQueue to wait for a paging queue to finish all operations queued to it and destroy it along with the associated sync object.
old-location: display\d3dddi_destroypagingqueue.htm
tech.root: display
ms.assetid: CBCE6C4C-C713-4ED3-9C40-30F9D8C2406D
ms.date: 05/10/2018
keywords: ["D3DDDI_DESTROYPAGINGQUEUE structure"]
ms.keywords: D3DDDI_DESTROYPAGINGQUEUE, D3DDDI_DESTROYPAGINGQUEUE structure [Display Devices], d3dukmdt/D3DDDI_DESTROYPAGINGQUEUE, display.d3dddi_destroypagingqueue
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: D3DDDI_DESTROYPAGINGQUEUE
f1_keywords:
 - D3DDDI_DESTROYPAGINGQUEUE
 - d3dukmdt/D3DDDI_DESTROYPAGINGQUEUE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - D3DDDI_DESTROYPAGINGQUEUE
---

# D3DDDI_DESTROYPAGINGQUEUE structure


## -description

<b>D3DDDI_DESTROYPAGINGQUEUE</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroypagingqueuecb">pfnDestroyPagingQueueCb</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtdestroypagingqueue">D3DKMTDestroyPagingQueue</a> to wait for a paging queue to finish all operations queued to it and destroy it along with the associated sync object.

## -struct-fields

### -field hPagingQueue

[in] A paging queue handle to be destroyed.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtdestroypagingqueue">D3DKMTDestroyPagingQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroypagingqueuecb">pfnDestroyPagingQueueCb</a>

