---
UID: NS:d3dukmdt.D3DDDI_DESTROYPAGINGQUEUE
title: D3DDDI_DESTROYPAGINGQUEUE
author: windows-driver-content
description: D3DDDI_DESTROYPAGINGQUEUE is used with pfnDestroyPagingQueueCb and D3DKMTDestroyPagingQueue to wait for a paging queue to finish all operations queued to it and destroy it along with the associated sync object.
old-location: display\d3dddi_destroypagingqueue.htm
old-project: display
ms.assetid: CBCE6C4C-C713-4ED3-9C40-30F9D8C2406D
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDI_DESTROYPAGINGQUEUE, D3DDDI_DESTROYPAGINGQUEUE structure [Display Devices], d3dukmdt/D3DDDI_DESTROYPAGINGQUEUE, display.d3dddi_destroypagingqueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dukmdt.h
api_name:
-	D3DDDI_DESTROYPAGINGQUEUE
product: Windows
targetos: Windows
req.typenames: D3DDDI_DESTROYPAGINGQUEUE
---

# D3DDDI_DESTROYPAGINGQUEUE structure


## -description


<b>D3DDDI_DESTROYPAGINGQUEUE</b> is used with <a href="https://msdn.microsoft.com/2C039656-5384-4864-8F29-A336B0ED06C0">pfnDestroyPagingQueueCb</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/dn906773">D3DKMTDestroyPagingQueue</a> to wait for a paging queue to finish all operations queued to it and destroy it along with the associated sync object.


## -struct-fields




### -field hPagingQueue

[in] A paging queue handle to be destroyed.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906773">D3DKMTDestroyPagingQueue</a>



<a href="https://msdn.microsoft.com/2C039656-5384-4864-8F29-A336B0ED06C0">pfnDestroyPagingQueueCb</a>
 

 

