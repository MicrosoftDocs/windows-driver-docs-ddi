---
UID: NC:d3dumddi.PFND3DDDI_DESTROYHWCONTEXTCB
title: PFND3DDDI_DESTROYHWCONTEXTCB
author: windows-driver-content
description: A callback to destroy a hardware context.
old-location: display\pfnd3dddi_destroyhwcontextcb.htm
tech.root: display
ms.assetid: CD3B8EE1-8B54-4F0A-B3C7-3B6F7D968497
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3DDDI_DESTROYHWCONTEXTCB, PFND3DDDI_DESTROYHWCONTEXTCB callback, PFND3DDDI_DESTROYHWCONTEXTCB callback function [Display Devices], d3dumddi/PFND3DDDI_DESTROYHWCONTEXTCB, display.pfnd3dddi_destroyhwcontextcb
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	PFND3DDDI_DESTROYHWCONTEXTCB
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DESTROYHWCONTEXTCB callback function


## -description


A callback to destroy a hardware context.


## -parameters




### -param hDevice [in]

A handle to the device.


### -param *

*destroyHwContext* [in]

A pointer to the structure holding information to destroy the hardware context.


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



