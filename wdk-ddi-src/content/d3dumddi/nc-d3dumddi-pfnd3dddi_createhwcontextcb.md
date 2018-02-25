---
UID: NC:d3dumddi.PFND3DDDI_CREATEHWCONTEXTCB
title: PFND3DDDI_CREATEHWCONTEXTCB
author: windows-driver-content
description: A callback to create a new hardware context.
old-location: display\pfnd3dddi_createhwcontextcb.htm
old-project: display
ms.assetid: 989682F3-340E-4F64-BF2D-771D58066EB2
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFND3DDDI_CREATEHWCONTEXTCB, PFND3DDDI_CREATEHWCONTEXTCB callback function [Display Devices], d3dumddi/PFND3DDDI_CREATEHWCONTEXTCB, display.pfnd3dddi_createhwcontextcb
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
-	PFND3DDDI_CREATEHWCONTEXTCB
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_CREATEHWCONTEXTCB callback


## -description


A callback to create a new hardware context.


## -prototype


````
_Check_return_ HRESULT APIENTRY CALLBACK PFND3DDDI_CREATEHWCONTEXTCB(
  _In_    HANDLE                          hDevice,
  _Inout_ D3DDDICB_CREATEHWCONTEXT *const createHwContext
);
````


## -parameters




### -param hDevice [in]

A handle to the device.


### -param *








#### - createHwContext [in, out]

A pointer to the structure holding information on creating the hardware context.


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



