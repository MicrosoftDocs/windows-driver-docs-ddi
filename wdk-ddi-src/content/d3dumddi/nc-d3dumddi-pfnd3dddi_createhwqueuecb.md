---
UID: NC:d3dumddi.PFND3DDDI_CREATEHWQUEUECB
title: PFND3DDDI_CREATEHWQUEUECB
author: windows-driver-content
description: A callback to create a new hardware queue.
old-location: display\pfnd3dddi_createhwqueuecb.htm
old-project: display
ms.assetid: 1BA2E4DD-3E91-4D2E-AA90-9C85D53EE9E3
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.pfnd3dddi_createhwqueuecb, PFND3DDDI_CREATEHWQUEUECB callback function [Display Devices], PFND3DDDI_CREATEHWQUEUECB, d3dumddi/PFND3DDDI_CREATEHWQUEUECB
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
-	PFND3DDDI_CREATEHWQUEUECB
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_CREATEHWQUEUECB callback


## -description


A callback to create a new hardware queue


## -prototype


````
_Check_return_ HRESULT APIENTRY CALLBACK PFND3DDDI_CREATEHWQUEUECB(
  _In_    HANDLE                        hDevice,
  _Inout_ D3DDDICB_CREATEHWQUEUE *const createHwQueue
);
````


## -parameters




### -param hDevice [in]

A handle to the device.


### -param *








#### - createHwQueue [in, out]

A pointer to the structure holding information on creating the hardware queue.


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



