---
UID: NS:d3d10umddi.D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT (d3d10umddi.h)
description: The D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure describes the geometry shader with stream output to create.
old-location: display\d3d11ddiarg_creategeometryshaderwithstreamoutput.htm
ms.date: 05/10/2018
keywords: ["D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure"]
ms.keywords: D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure [Display Devices], UMDisplayDriver_Dx11param_Structs_6b81cccd-92f9-4135-8bcc-d523b514c45c.xml, d3d10umddi/D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, display.d3d11ddiarg_creategeometryshaderwithstreamoutput
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT is supported beginning with the Windows 7 operating system.
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
tech.root: display
req.typenames: D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
f1_keywords:
 - D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
 - d3d10umddi/D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
---

# D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure


## -description

The D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure describes the geometry shader with stream output to create.

## -struct-fields

### -field pShaderCode [in]

An array of CONST UINT tokens that make up the geometry shader code.

### -field pOutputStreamDecl [in]

An array of <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_stream_output_declaration_entry">D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY</a> structures that describes the stream output for the geometry shader.

### -field NumEntries [in]

The number of elements in that array that the <b>pOutputStreamDecl</b> member specifies.

### -field BufferStridesInBytes [in]

An array of strides (bytes from one vertex to the next vertex).

### -field NumStrides [in]

The number of strides in the array that the <b>BufferStridesInBytes</b> member specifies.

### -field RasterizedStream [in]

A value that identifies the rasterized stream.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivategeometryshaderwithstreamoutput">CalcPrivateGeometryShaderWithStreamOutput</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_creategeometryshaderwithstreamoutput">CreateGeometryShaderWithStreamOutput</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_stream_output_declaration_entry">D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY</a>
