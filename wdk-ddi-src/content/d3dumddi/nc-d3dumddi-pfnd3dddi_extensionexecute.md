---
UID: NC:d3dumddi.PFND3DDDI_EXTENSIONEXECUTE
title: PFND3DDDI_EXTENSIONEXECUTE (d3dumddi.h)
description: Learn more about the PFND3DDDI_EXTENSIONEXECUTE callback function.
tech.root: display
ms.date: 09/10/2024
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
 - PFND3DDDI_EXTENSIONEXECUTE
---

# PFND3DDDI_EXTENSIONEXECUTE callback function

## -description

The **ExtensionExecute** function performs an operation by using the given DirectX Video Accelerator (DXVA) extension device.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param unnamedParam2

*pData* [in]

A pointer to a [**D3DDDIARG_EXTENSIONEXECUTE**](ns-d3dumddi-_d3dddiarg_extensionexecute.md) structure that describes the DXVA operation to perform.

## -returns

**ExtensionExecute** returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The DXVA operation is successfully performed.|
|E_OUTOFMEMORY|ExtensionExecute could not allocate the required memory for it to complete.|

## -remarks

For more information, see [Extended Support for DirectX VA 2.0](/windows-hardware/drivers/display/extended-support-for-directx-va-2-0).

## -see-also

[**CreateExtensionDevice**](nc-d3dumddi-pfnd3dddi_createextensiondevice.md)

[**D3DDDIARG_EXTENSIONEXECUTE**](ns-d3dumddi-_d3dddiarg_extensionexecute.md)

[**D3DDDI_DEVICEFUNCS**](ns-d3dumddi-_d3dddi_devicefuncs.md)
