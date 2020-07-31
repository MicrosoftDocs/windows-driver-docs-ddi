---
UID: NC:d3dumddi.PFND3DDDI_CREATEEXTENSIONDEVICE
title: PFND3DDDI_CREATEEXTENSIONDEVICE (d3dumddi.h)
description: The CreateExtensionDevice function creates a Microsoft DirectX Video Acceleration (DirectX VA) extension device.
old-location: display\createextensiondevice.htm
tech.root: display
ms.assetid: 7e6dbb70-2e74-4ddb-a504-2c8145af99d9
ms.date: 05/10/2018
keywords: ["PFND3DDDI_CREATEEXTENSIONDEVICE callback function"]
ms.keywords: CreateExtensionDevice, CreateExtensionDevice callback function [Display Devices], PFND3DDDI_CREATEEXTENSIONDEVICE, PFND3DDDI_CREATEEXTENSIONDEVICE callback, UserModeDisplayDriver_Functions_342ee084-e24a-43a8-99a9-c83c2670e2e4.xml, d3dumddi/CreateExtensionDevice, display.createextensiondevice
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
 - "d3dumddi/CreateExtensionDevice"
 - "CreateExtensionDevice"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - CreateExtensionDevice
product:
 - Windows
---

# PFND3DDDI_CREATEEXTENSIONDEVICE callback function

## -description

The <b>CreateExtensionDevice</b> function creates a Microsoft DirectX Video Acceleration (DirectX VA) extension device.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createextensiondevice">D3DDDIARG_CREATEEXTENSIONDEVICE</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information in the structure that the Microsoft Direct3D runtime can use.

## -returns

<b>CreateExtensionDevice</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The extension device is successfully created. | 
| **E_OUTOFMEMORY** | [CreateExtensionDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createextensiondevice)  could not allocate the required memory for it to complete. |

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createextensiondevice">D3DDDIARG_CREATEEXTENSIONDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroyextensiondevice">DestroyExtensionDevice</a>

