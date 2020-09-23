---
UID: NC:d3dumddi.PFND3DDDI_EXTENSIONEXECUTE
title: PFND3DDDI_EXTENSIONEXECUTE (d3dumddi.h)
description: The ExtensionExecute function performs an operation by using the given Microsoft DirectX Video Accelerator (VA) extension device.
old-location: display\extensionexecute.htm
tech.root: display
ms.assetid: a3f73651-bfff-48fa-aa61-477b8af7fa07
ms.date: 05/10/2018
keywords: ["PFND3DDDI_EXTENSIONEXECUTE callback function"]
ms.keywords: ExtensionExecute, ExtensionExecute callback function [Display Devices], PFND3DDDI_EXTENSIONEXECUTE, PFND3DDDI_EXTENSIONEXECUTE callback, UserModeDisplayDriver_Functions_2972e743-bdb5-41ab-92ff-986b8335883b.xml, d3dumddi/ExtensionExecute, display.extensionexecute
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
 - PFND3DDDI_EXTENSIONEXECUTE
 - d3dumddi/PFND3DDDI_EXTENSIONEXECUTE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - ExtensionExecute
product:
 - Windows
---

# PFND3DDDI_EXTENSIONEXECUTE callback function


## -description

The <i>ExtensionExecute</i> function performs an operation by using the given Microsoft DirectX Video Accelerator (VA) extension device.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_extensionexecute">D3DDDIARG_EXTENSIONEXECUTE</a> structure that describes the DirectX VA operation to perform.

## -returns

<i>ExtensionExecute</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The DirectX VA operation is successfully performed.|
|E_OUTOFMEMORY|ExtensionExecute could not allocate the required memory for it to complete.|

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_extensionexecute">D3DDDIARG_EXTENSIONEXECUTE</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>