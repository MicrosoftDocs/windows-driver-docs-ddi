---
UID: NS:d3d10umddi.D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT (d3d10umddi.h)
description: The D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure describes the geometry shader with stream output to create.
old-location: display\d3d10ddiarg_creategeometryshaderwithstreamoutput.htm
ms.date: 05/10/2018
keywords: ["D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure"]
ms.keywords: D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure [Display Devices], UMDisplayDriver_Dx10param_Structs_c41e18d8-8aca-4902-b921-0916f3ca2042.xml, d3d10umddi/D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, display.d3d10ddiarg_creategeometryshaderwithstreamoutput
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
tech.root: display
req.typenames: D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
f1_keywords:
 - D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
 - d3d10umddi/D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
---

# D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure


## -description

The D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure describes the geometry shader with stream output to create.

## -struct-fields

### -field pShaderCode [in]

An array of CONST UINT tokens that make up the geometry shader code.

### -field pOutputStreamDecl [in]

An array of <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_stream_output_declaration_entry">D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY</a> structures that describes the stream output for the geometry shader.

### -field NumEntries [in]

The number of elements in that array that the <b>pOutputStreamDecl</b> member specifies.

### -field StreamOutputStrideInBytes [in]

The size, in bytes, from one vertex to the next vertex.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivategeometryshaderwithstreamoutput">CalcPrivateGeometryShaderWithStreamOutput</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_creategeometryshaderwithstreamoutput">CreateGeometryShaderWithStreamOutput</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_stream_output_declaration_entry">D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY</a>
