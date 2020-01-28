---
UID: NC:d3dumddi.PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB
title: PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB (d3dumddi.h)
description: A callback to submit a command to the hardware queue.
old-location: display\pfnd3dddi_submitcommandtohwqueuecb.htm
tech.root: display
ms.assetid: 8E8B0FE6-ACE5-4610-A0F7-95D426A4AA97
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB, PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB callback, PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB callback function [Display Devices], d3dumddi/PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB, display.pfnd3dddi_submitcommandtohwqueuecb
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
 - "d3dumddi/PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB
product:
 - Windows
---

# PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB callback function

## -description

A callback to submit a command to the hardware queue.

## -parameters

### -param hDevice

A handle to the device.

### -param Arg2

*submitCommandToHwQueue* [in]

A pointer to the structure holding information on submitting a command to the hardware queue.

## -returns

|Return code|Description|
|--|--|
|S_OK|The call was completed successfully.|


This function might also return other HRESULT values.

