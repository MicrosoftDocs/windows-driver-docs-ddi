---
UID: NC:d3dumddi.PFND3DDDI_SUBMITWAITFORSYNCOBJECTSTOHWQUEUECB
title: PFND3DDDI_SUBMITWAITFORSYNCOBJECTSTOHWQUEUECB (d3dumddi.h)
description: A callback to submit a wait command to the hardware queue.
old-location: display\pfnd3dddi_submitwaitforsyncobjectstohwqueuecb.htm
tech.root: display
ms.assetid: 4FD92529-0F47-46FC-9567-D8C0A5D76728
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SUBMITWAITFORSYNCOBJECTSTOHWQUEUECB, PFND3DDDI_SUBMITWAITFORSYNCOBJECTSTOHWQUEUECB callback, PFND3DDDI_SUBMITWAITFORSYNCOBJECTSTOHWQUEUECB callback function [Display Devices], d3dumddi/PFND3DDDI_SUBMITWAITFORSYNCOBJECTSTOHWQUEUECB, display.pfnd3dddi_submitwaitforsyncobjectstohwqueuecb
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dumddi.h
api_name:
- PFND3DDDI_SUBMITWAITFORSYNCOBJECTSTOHWQUEUECB
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SUBMITWAITFORSYNCOBJECTSTOHWQUEUECB callback function


## -description


A callback to submit a wait command to the hardware queue.


## -parameters




### -param hDevice [in]

A handle to the device.


### -param *

*submitWaitForSyncObjectsToHwQueue* [in]

A pointer to the structure holding information on submitting a wait command to the hardware queue.


## -returns

|Return code|Description|
|--- |--- |
|S_OK|The call was successfully completed.|

This function might also return other HRESULT values.



