---
UID: NC:d3dumddi.PFND3DDDI_DESTROYHWQUEUECB
title: PFND3DDDI_DESTROYHWQUEUECB (d3dumddi.h)
description: A callback to destroy a hardware queue.
old-location: display\pfnd3dddi_destroyhwqueuecb.htm
tech.root: display
ms.assetid: F3578E0E-2249-4BC2-B776-E6356D523059
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_DESTROYHWQUEUECB, PFND3DDDI_DESTROYHWQUEUECB callback, PFND3DDDI_DESTROYHWQUEUECB callback function [Display Devices], d3dumddi/PFND3DDDI_DESTROYHWQUEUECB, display.pfnd3dddi_destroyhwqueuecb
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
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/PFND3DDDI_DESTROYHWQUEUECB"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_DESTROYHWQUEUECB
product:
 - Windows
---

# PFND3DDDI_DESTROYHWQUEUECB callback function

## -description

A callback to destroy a hardware queue.

## -parameters

### -param hDevice

A handle to the device.

### -param Arg2

*destroyHwQueue* [in]

A pointer to the structure holding information to destroy the hardware queue.

## -returns

|Return code|Description|
|--- |--- |
|S_OK|The call was successfully completed.|

This function might also return other HRESULT values.

