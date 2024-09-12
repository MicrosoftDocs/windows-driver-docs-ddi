---
UID: NC:d3dumddi.PFND3DDDI_CREATEEXTENSIONDEVICE
title: PFND3DDDI_CREATEEXTENSIONDEVICE (d3dumddi.h)
description: Learn more about the PFND3DDDI_CREATEEXTENSIONDEVICE callback function.
tech.root: display
ms.date: 09/09/2024
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
 - PFND3DDDI_CREATEEXTENSIONDEVICE
 - d3dumddi/PFND3DDDI_CREATEEXTENSIONDEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_CREATEEXTENSIONDEVICE
---

# PFND3DDDI_CREATEEXTENSIONDEVICE callback function

## -description

The **CreateExtensionDevice** function creates a DirectX Video Acceleration (DXVA) extension device.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param unnamedParam2

*pData* [in, out]

A pointer to a [**D3DDDIARG_CREATEEXTENSIONDEVICE**](ns-d3dumddi-_d3dddiarg_createextensiondevice.md) structure. On input, this structure contains information that the driver can use. On output, the driver specifies information in the structure that the Direct3D runtime can use.

## -returns

**CreateExtensionDevice** returns one of the following values:

| **Return code** | **Description** |
|:--|:--|
| **S_OK** | The extension device is successfully created. |
| **E_OUTOFMEMORY** | **CreateExtensionDevice** couldn't allocate the required memory for it to complete. |

## -remarks

For more information, see [Creating and Using a DirectX VA 2.0 Extension Device](/windows-hardware/drivers/display/creating-and-using-a-directx-va-2-0-extension-device).

## -see-also

[**D3DDDIARG_CREATEEXTENSIONDEVICE**](ns-d3dumddi-_d3dddiarg_createextensiondevice.md)

[**DecodeExtensionExecute**](nc-d3dumddi-pfnd3dddi_decodeextensionexecute.md)

[**DestroyExtensionDevice**](nc-d3dumddi-pfnd3dddi_destroyextensiondevice.md)
