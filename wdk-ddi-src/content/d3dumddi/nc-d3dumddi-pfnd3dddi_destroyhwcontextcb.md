---
UID: NC:d3dumddi.PFND3DDDI_DESTROYHWCONTEXTCB
title: PFND3DDDI_DESTROYHWCONTEXTCB
description: A callback to destroy a hardware context.
old-location: display\pfnd3dddi_destroyhwcontextcb.htm
tech.root: display
ms.assetid: CD3B8EE1-8B54-4F0A-B3C7-3B6F7D968497
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_DESTROYHWCONTEXTCB, PFND3DDDI_DESTROYHWCONTEXTCB callback, PFND3DDDI_DESTROYHWCONTEXTCB callback function [Display Devices], d3dumddi/PFND3DDDI_DESTROYHWCONTEXTCB, display.pfnd3dddi_destroyhwcontextcb
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

|Return code|Description|
|--- |--- |
|S_OK|The call was successfully completed.|
 

This function might also return other HRESULT values.



