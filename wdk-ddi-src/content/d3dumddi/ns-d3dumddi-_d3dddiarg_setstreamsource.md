---
UID: NS:d3dumddi._D3DDDIARG_SETSTREAMSOURCE
title: "_D3DDDIARG_SETSTREAMSOURCE"
author: windows-driver-content
description: The D3DDDIARG_SETSTREAMSOURCE structure describes the portion of the vertex stream to bind to a vertex buffer.
old-location: display\d3dddiarg_setstreamsource.htm
old-project: display
ms.assetid: 6a178ef0-0741-4b0c-a688-cae3923135ac
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDisplayDriver_param_Structs_f90eed83-1d01-4502-84e4-22cff72016d6.xml, display.d3dddiarg_setstreamsource, D3DDDIARG_SETSTREAMSOURCE, _D3DDDIARG_SETSTREAMSOURCE, D3DDDIARG_SETSTREAMSOURCE structure [Display Devices], d3dumddi/D3DDDIARG_SETSTREAMSOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
apiname:
-	D3DDDIARG_SETSTREAMSOURCE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETSTREAMSOURCE
---

# _D3DDDIARG_SETSTREAMSOURCE structure


## -description


The D3DDDIARG_SETSTREAMSOURCE structure describes the portion of the vertex stream to bind to a vertex buffer. 


## -syntax


````
typedef struct _D3DDDIARG_SETSTREAMSOURCE {
  UINT   Stream;
  HANDLE hVertexBuffer;
  UINT   Offset;
  UINT   Stride;
} D3DDDIARG_SETSTREAMSOURCE;
````


## -struct-fields




#### - Stream

[in] The stream to bind, which is a value between zero and the maximum number of streams that are specified by the driver.


#### - hVertexBuffer

[in] A handle to the vertex buffer. If this member is zero, the stream should no longer be bound to a vertex buffer.


#### - Offset

[in] The offset in bytes into the stream. 

The <b>Offset</b> value must be DWORD-aligned.


#### - Stride

[in] The size, in bytes, from one vertex to the next vertex. If <b>Stride</b> is set to zero, all of the vertices receive the same data for processing. 

For example, an application might use two input source streams where the first stream contains position information and the second stream contains normal information. If stride for the second stream is set to zero, all of the vertices in the second stream use the same normal information, which is the first normal information that occurs in the second stream.

The <b>Stride</b> value must be DWORD-aligned.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setstreamsource.md">SetStreamSource</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETSTREAMSOURCE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

