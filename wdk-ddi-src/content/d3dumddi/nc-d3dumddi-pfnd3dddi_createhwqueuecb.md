---
UID: NC:d3dumddi.PFND3DDDI_CREATEHWQUEUECB
title: PFND3DDDI_CREATEHWQUEUECB (d3dumddi.h)
description: A callback to create a new hardware queue.
old-location: display\pfnd3dddi_createhwqueuecb.htm
tech.root: display
ms.assetid: 1BA2E4DD-3E91-4D2E-AA90-9C85D53EE9E3
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_CREATEHWQUEUECB, PFND3DDDI_CREATEHWQUEUECB callback, PFND3DDDI_CREATEHWQUEUECB callback function [Display Devices], d3dumddi/PFND3DDDI_CREATEHWQUEUECB, display.pfnd3dddi_createhwqueuecb
ms.topic: callback
f1_keywords:
 - "d3dumddi/PFND3DDDI_CREATEHWQUEUECB"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dumddi.h
api_name:
- PFND3DDDI_CREATEHWQUEUECB
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CREATEHWQUEUECB callback function


## -description


A callback to create a new hardware queue


## -parameters




### -param hDevice [in]

A handle to the device.


### -param *

*createHwQueue* [in, out]

A pointer to the structure holding information on creating the hardware queue.


## -returns

|Return code|Description|
|--- |--- |
|S_OK|The call was successfully completed.|
 

This function might also return other HRESULT values.



