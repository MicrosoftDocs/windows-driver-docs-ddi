---
UID: NC:d3dumddi.PFND3DDDI_DESTROYPAGINGQUEUECB
title: PFND3DDDI_DESTROYPAGINGQUEUECB
author: windows-driver-content
description: pfnDestroyPagingQueueCb waits for a paging queue to finish all operations queued to it and destroys it along with the associated sync object.
old-location: display\pfndestroypagingqueuecb.htm
tech.root: display
ms.assetid: 2C039656-5384-4864-8F29-A336B0ED06C0
ms.date: 5/10/2018
ms.keywords: PFND3DDDI_DESTROYPAGINGQUEUECB, PFND3DDDI_DESTROYPAGINGQUEUECB callback, d3dumddi/pfnDestroyPagingQueueCb, display.pfndestroypagingqueuecb, pfnDestroyPagingQueueCb, pfnDestroyPagingQueueCb callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	pfnDestroyPagingQueueCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DESTROYPAGINGQUEUECB callback function


## -description


<b>pfnDestroyPagingQueueCb</b> waits for a paging queue to finish all operations queued to it and destroys it along with the associated sync object.


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906321">D3DDDI_DESTROYPAGINGQUEUE</a> structure that describes the operation to perform.




## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



In addition to <b>hPagingQueue</b>, this device driver interface (DDI) invalidates <b>hSyncObject</b> and <b>FenceValueCPUVirtualAddress</b> values returned from <a href="https://msdn.microsoft.com/99E4CFCF-7A0A-43A9-9E23-B7A9F9375690">pfnCreatePagingQueueCb</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906321">D3DDDI_DESTROYPAGINGQUEUE</a>



<a href="https://msdn.microsoft.com/99E4CFCF-7A0A-43A9-9E23-B7A9F9375690">pfnCreatePagingQueueCb</a>
 

 

