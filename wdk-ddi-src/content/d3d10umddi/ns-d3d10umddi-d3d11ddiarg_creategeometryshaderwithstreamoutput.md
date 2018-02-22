---
UID: NS:d3d10umddi.D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
author: windows-driver-content
description: The D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure describes the geometry shader with stream output to create.
old-location: display\d3d11ddiarg_creategeometryshaderwithstreamoutput.htm
old-project: display
ms.assetid: 07ad9fdb-16f0-4752-9b35-e69d6a7b8815
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.d3d11ddiarg_creategeometryshaderwithstreamoutput, d3d10umddi/D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure [Display Devices], UMDisplayDriver_Dx11param_Structs_6b81cccd-92f9-4135-8bcc-d523b514c45c.xml, D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
product: Windows
targetos: Windows
req.typenames: D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
---

# D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure


## -description


The D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure describes the geometry shader with stream output to create. 


## -syntax


````
typedef struct D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT {
  const UINT                                        *pShaderCode;
  const D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY *pOutputStreamDecl;
  UINT                                              NumEntries;
  const UINT                                        *BufferStridesInBytes;
  UINT                                              NumStrides;
  UINT                                              RasterizedStream;
} D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT;
````


## -struct-fields




### -field pShaderCode

[in] An array of CONST UINT tokens that make up the geometry shader code. 


### -field pOutputStreamDecl

[in] An array of <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_stream_output_declaration_entry.md">D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY</a> structures that describes the stream output for the geometry shader. 


### -field NumEntries

[in] The number of elements in that array that the <b>pOutputStreamDecl</b> member specifies. 


### -field BufferStridesInBytes

[in] An array of strides (bytes from one vertex to the next vertex). 


### -field NumStrides

[in] The number of strides in the array that the <b>BufferStridesInBytes</b> member specifies. 


### -field RasterizedStream

[in] A value that identifies the rasterized stream. 


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_stream_output_declaration_entry.md">D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_creategeometryshaderwithstreamoutput.md">CreateGeometryShaderWithStreamOutput</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivategeometryshaderwithstreamoutput.md">CalcPrivateGeometryShaderWithStreamOutput</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

