---
UID: NS:d3dumddi._D3DDDIARG_SETINDICES
title: "_D3DDDIARG_SETINDICES"
author: windows-driver-content
description: The D3DDDIARG_SETINDICES structure describes parameters for setting the current index buffer.
old-location: display\d3dddiarg_setindices.htm
old-project: display
ms.assetid: 9a0b8706-91ba-42a5-aaa2-0381931d64f0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIARG_SETINDICES structure [Display Devices], D3DDDIARG_SETINDICES, _D3DDDIARG_SETINDICES, d3dumddi/D3DDDIARG_SETINDICES, UMDisplayDriver_param_Structs_68458ee2-76c8-41c5-b610-47ef40874c1e.xml, display.d3dddiarg_setindices
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
-	D3DDDIARG_SETINDICES
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETINDICES
---

# _D3DDDIARG_SETINDICES structure


## -description


The D3DDDIARG_SETINDICES structure describes parameters for setting the current index buffer. 


## -syntax


````
typedef struct _D3DDDIARG_SETINDICES {
  HANDLE hIndexBuffer;
  UINT   Stride;
} D3DDDIARG_SETINDICES;
````


## -struct-fields




### -field hIndexBuffer

[in] A handle to the surface that is associated with the index buffer.


### -field Stride

[in] The size, in bytes, of the indices that are contained in the index buffer. The value of this member is 2 if the indices are 16-bit quantities or 4 if the indices are 32-bit quantities.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setstreamsourceum.md">SetStreamSourceUM</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setindices.md">SetIndices</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETINDICES structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

