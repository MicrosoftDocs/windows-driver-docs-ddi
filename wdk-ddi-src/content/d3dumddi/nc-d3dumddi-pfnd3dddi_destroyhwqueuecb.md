---
UID: NC:d3dumddi.PFND3DDDI_DESTROYHWQUEUECB
title: PFND3DDDI_DESTROYHWQUEUECB
author: windows-driver-content
description: A callback to destroy a hardware queue.
old-location: display\pfnd3dddi_destroyhwqueuecb.htm
old-project: display
ms.assetid: F3578E0E-2249-4BC2-B776-E6356D523059
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFND3DDDI_DESTROYHWQUEUECB
req.alt-loc: d3dumddi.h
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_DESTROYHWQUEUECB callback



## -description
A callback to destroy a hardware queue.



## -prototype

````
_Check_return_ HRESULT APIENTRY CALLBACK PFND3DDDI_DESTROYHWQUEUECB(
  _In_ HANDLE                         hDevice,
  _In_ D3DDDICB_DESTROYHWQUEUE *const destroyHwQueue
);
````


## -parameters

### -param hDevice [in]

A handle to the device.


### -param destroyHwQueue [in]

A pointer to the structure holding information to destroy the hardware queue.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The call was successfully completed.

 

This function might also return other HRESULT values.


## -remarks
