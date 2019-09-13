---
UID: NC:d3dumddi.PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB
title: PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB (d3dumddi.h)
description: A callback to submit a signal command to the hardware queue.
old-location: display\pfnd3dddi_submitsignalsyncobjectstohwqueuecb.htm
tech.root: display
ms.assetid: D952A432-7B2C-43AC-9BC4-4335D2F37301
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB, PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB callback, PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB callback function [Display Devices], d3dumddi/PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB, display.pfnd3dddi_submitsignalsyncobjectstohwqueuecb
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
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB
product:
 - Windows
---

# PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB callback function

## -description

A callback to submit a signal command to the hardware queue.

## -parameters

### -param hDevice

A handle to the device.

### -param Arg2

*submitSignalSyncoObjectsToHwQueue* [in]

A pointer to the structure holding information on submitting a signal command to the hardware queue.

## -returns

|Return code|Description|
|--- |--- |
|S_OK|The call was successfully completed.|

This function might also return other HRESULT values.

