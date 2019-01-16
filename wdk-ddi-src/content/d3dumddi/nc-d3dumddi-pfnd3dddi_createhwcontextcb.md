---
UID: NC:d3dumddi.PFND3DDDI_CREATEHWCONTEXTCB
title: PFND3DDDI_CREATEHWCONTEXTCB
description: A callback to create a new hardware context.
old-location: display\pfnd3dddi_createhwcontextcb.htm
tech.root: display
ms.assetid: 989682F3-340E-4F64-BF2D-771D58066EB2
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_CREATEHWCONTEXTCB, PFND3DDDI_CREATEHWCONTEXTCB callback, PFND3DDDI_CREATEHWCONTEXTCB callback function [Display Devices], d3dumddi/PFND3DDDI_CREATEHWCONTEXTCB, display.pfnd3dddi_createhwcontextcb
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
-	PFND3DDDI_CREATEHWCONTEXTCB
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CREATEHWCONTEXTCB callback function


## -description


A callback to create a new hardware context.


## -parameters




### -param hDevice [in]

A handle to the device.


### -param *

*createHwContext* [in, out]

A pointer to the structure holding information on creating the hardware context.


## -returns

|Return code|Description|
|--- |--- |
|S_OK|The call was successfully completed.|
 

This function might also return other HRESULT values.



