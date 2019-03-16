---
UID: NS:d3d10umddi.D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT (d3d10umddi.h)
description: The D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure describes the geometry shader with stream output to create.
old-location: display\d3d11ddiarg_creategeometryshaderwithstreamoutput.htm
ms.assetid: 07ad9fdb-16f0-4752-9b35-e69d6a7b8815
ms.date: 05/10/2018
ms.keywords: D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure [Display Devices], UMDisplayDriver_Dx11param_Structs_6b81cccd-92f9-4135-8bcc-d523b514c45c.xml, d3d10umddi/D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, display.d3d11ddiarg_creategeometryshaderwithstreamoutput
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
---

# D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure


## -description


The D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure describes the geometry shader with stream output to create. 


## -struct-fields




### -field pShaderCode

[in] An array of CONST UINT tokens that make up the geometry shader code. 


### -field pOutputStreamDecl

[in] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542097">D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY</a> structures that describes the stream output for the geometry shader. 


### -field NumEntries

[in] The number of elements in that array that the <b>pOutputStreamDecl</b> member specifies. 


### -field BufferStridesInBytes

[in] An array of strides (bytes from one vertex to the next vertex). 


### -field NumStrides

[in] The number of strides in the array that the <b>BufferStridesInBytes</b> member specifies. 


### -field RasterizedStream

[in] A value that identifies the rasterized stream. 


## -see-also




<a href="https://msdn.microsoft.com/3e760b93-e859-4175-a24a-6bf3648db6db">CalcPrivateGeometryShaderWithStreamOutput</a>



<a href="https://msdn.microsoft.com/6ad1573d-4377-4795-8511-5d6cae96ee4f">CreateGeometryShaderWithStreamOutput</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542097">D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY</a>
 

 

