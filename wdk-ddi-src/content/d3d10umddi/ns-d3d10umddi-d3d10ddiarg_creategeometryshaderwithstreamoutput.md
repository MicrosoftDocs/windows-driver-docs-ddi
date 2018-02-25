---
UID: NS:d3d10umddi.D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
author: windows-driver-content
description: The D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure describes the geometry shader with stream output to create.
old-location: display\d3d10ddiarg_creategeometryshaderwithstreamoutput.htm
old-project: display
ms.assetid: 172af07e-9cc7-48d1-900a-93f18bdc37a9
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 0, 1, 3, A, C, D, D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure [Display Devices], E, G, H, I, M, O, P, R, S, T, U, UMDisplayDriver_Dx10param_Structs_c41e18d8-8aca-4902-b921-0916f3ca2042.xml, W, Y, _, d3d10umddi/D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, display.d3d10ddiarg_creategeometryshaderwithstreamoutput"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
---

# D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure


## -description


The D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure describes the geometry shader with stream output to create.


## -syntax


````
typedef struct D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT {
  const UINT                                        *pShaderCode;
  const D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY *pOutputStreamDecl;
  UINT                                              NumEntries;
  UINT                                              StreamOutputStrideInBytes;
} D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT;
````


## -struct-fields




### -field pShaderCode

[in] An array of CONST UINT tokens that make up the geometry shader code.


### -field pOutputStreamDecl

[in] An array of <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_stream_output_declaration_entry.md">D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY</a> structures that describes the stream output for the geometry shader. 


### -field NumEntries

[in] The number of elements in that array that the <b>pOutputStreamDecl</b> member specifies. 


### -field StreamOutputStrideInBytes

[in] The size, in bytes, from one vertex to the next vertex.


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_stream_output_declaration_entry.md">D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivategeometryshaderwithstreamoutput.md">CalcPrivateGeometryShaderWithStreamOutput</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_creategeometryshaderwithstreamoutput.md">CreateGeometryShaderWithStreamOutput</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

