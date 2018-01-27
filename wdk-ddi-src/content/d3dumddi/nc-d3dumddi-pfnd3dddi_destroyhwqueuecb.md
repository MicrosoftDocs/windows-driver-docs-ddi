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
ms.keywords: display.pfnd3dddi_destroyhwqueuecb, PFND3DDDI_DESTROYHWQUEUECB callback function [Display Devices], PFND3DDDI_DESTROYHWQUEUECB, d3dumddi/PFND3DDDI_DESTROYHWQUEUECB
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	d3dumddi.h
apiname: 
-	PFND3DDDI_DESTROYHWQUEUECB
product: Windows
targetos: Windows
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


### -param *






#### - destroyHwQueue [in]

A pointer to the structure holding information to destroy the hardware queue.


## -returns


<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The call was successfully completed.

</td>
</tr>
</table> 

This function might also return other HRESULT values.


