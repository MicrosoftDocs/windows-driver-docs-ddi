---
UID: NC:d3dumddi.PFND3DDDI_DECODEEXTENSIONEXECUTE
title: PFND3DDDI_DECODEEXTENSIONEXECUTE (d3dumddi.h)
description: Learn more about the PFND3DDDI_DECODEEXTENSIONEXECUTE callback function.
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
 - PFND3DDDI_DECODEEXTENSIONEXECUTE
 - d3dumddi/PFND3DDDI_DECODEEXTENSIONEXECUTE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_DECODEEXTENSIONEXECUTE
---

# PFND3DDDI_DECODEEXTENSIONEXECUTE callback function

## -description

The **DecodeExtensionExecute** function performs a decode operation by using the given DirectX Video Accelerator (DXVA) nonstandard, decode extension device.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param unnamedParam2

*pData* [in, out]

A pointer to a [**D3DDDIARG_DECODEEXTENSIONEXECUTE**](ns-d3dumddi-_d3dddiarg_decodeextensionexecute.md) structure that describes the DXVA decode operation to perform.

## -returns

**DecodeExtensionExecute** returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The DirectX VA decode operation is successfully performed.|
|E_OUTOFMEMORY|DecodeExtensionExecute could not allocate the required memory for it to complete.|

## -remarks

A user-mode display driver (UMD) can implement the **DecodeExtensionExecute** function to support extensions to the standard decode types (that is, nonstandard decode GUIDs). These nonstandard decode types are useful for configuring encryption and other miscellaneous enhancements.

**DecodeExtensionExecute** is called when DirectX VA 2.0 decoders require the nonstandard extensions.

For compatibility with DirectX VA 1.0 decoders that might require these nonstandard extensions, **DecodeExtensionExecute** is called whenever a DirectX VA 1.0 decoder makes an execution call in which any bDXVA_Func value that is greater than 4 is set in the most significant 8 bits of the **Function** member of the [**D3DDDIARG_DECODEEXTENSIONEXECUTE**](ns-d3dumddi-_d3dddiarg_decodeextensionexecute.md) structure. **DecodeExtensionExecute** is also called whenever DirectX VA 1.0 decoder makes a configuration call in which any DXVA_ConfigQueryOrReplyFunc flag other than DXVA_QUERYORREPLYFUNCFLAG_DECODER_PROBE_QUERY (0xFFFFF1) or DXVA_QUERYORREPLYFUNCFLAG_DECODER_LOCK_QUERY (0xFFFFF5) flag is set in the most significant 24 bits of **Function**. For more information about the meanings for the bit settings of **Function**, see the [DXVA_ConfigQueryOrReplyFlag and DXVA_ConfigQueryorReplyFunc Variables](/windows-hardware/drivers/display/dxva-configqueryorreplyflag-and-dxva-configqueryorreplyfunc-variables) and [bDXVA_Func Variable](/windows-hardware/drivers/display/bdxva-func-variable) topics.

Because of compatibility issues with DirectX VA 1.0 decoders that might make such a configuration call before DXVA_QUERYORREPLYFUNCFLAG_DECODER_LOCK_QUERY, those decoders can make such a configuration call also before a decode device is created. If such a configuration call is made before a decode device is created, the **hDecode** member of the [**D3DDDIARG_DECODEEXTENSIONEXECUTE**](ns-d3dumddi-_d3dddiarg_decodeextensionexecute.md) structure that the **pData** parameter points to is set to NULL. In this situation, the driver might be required to return an error (for example, E_FAIL) if the driver cannot support the situation independent of a decode device.

## -see-also

[**CreateExtensionDevice**](nc-d3dumddi-pfnd3dddi_createextensiondevice.md)

[**D3DDDIARG_DECODEEXTENSIONEXECUTE**](ns-d3dumddi-_d3dddiarg_decodeextensionexecute.md)

[**D3DDDI_DEVICEFUNCS**](ns-d3dumddi-_d3dddi_devicefuncs.md)
