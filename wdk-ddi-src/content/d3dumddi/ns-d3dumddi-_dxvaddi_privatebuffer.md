---
UID: NS:d3dumddi._DXVADDI_PRIVATEBUFFER
title: _DXVADDI_PRIVATEBUFFER
author: windows-driver-content
description: The DXVADDI_PRIVATEBUFFER structure describes a private buffer that a nonstandard decoder uses to perform a decode operation.
old-location: display\dxvaddi_privatebuffer.htm
old-project: display
ms.assetid: 3e41472c-4c9d-4727-af08-a350e1967ef0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXVADDI_PRIVATEBUFFER, DXVADDI_PRIVATEBUFFER
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
req.alt-api: DXVADDI_PRIVATEBUFFER
req.alt-loc: d3dumddi.h
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
req.typenames: DXVADDI_PRIVATEBUFFER
---

# _DXVADDI_PRIVATEBUFFER structure



## -description
The DXVADDI_PRIVATEBUFFER structure describes a private buffer that a nonstandard decoder uses to perform a decode operation. 



## -syntax

````
typedef struct _DXVADDI_PRIVATEBUFFER {
  HANDLE hResource;
  UINT   SubResourceIndex;
  UINT   DataOffset;
  UINT   DataSize;
} DXVADDI_PRIVATEBUFFER;
````


## -struct-fields

### -field hResource

[in] A handle to the resource that contains the private buffer for the decode operation. 


### -field SubResourceIndex

[in] The index to the private buffer within the resource.


### -field DataOffset

[in] The offset to the relevant data, in bytes, from the beginning of the buffer.


### -field DataSize

[in] The size of the relevant data, in bytes.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodeextensionexecute.md">D3DDDIARG_DECODEEXTENSIONEXECUTE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_PRIVATEBUFFER structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

