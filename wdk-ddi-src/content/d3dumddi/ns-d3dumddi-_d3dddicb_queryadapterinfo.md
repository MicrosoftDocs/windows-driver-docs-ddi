---
UID: NS:d3dumddi._D3DDDICB_QUERYADAPTERINFO
title: "_D3DDDICB_QUERYADAPTERINFO"
author: windows-driver-content
description: The D3DDDICB_QUERYADAPTERINFO structure contains information that describes the graphics adapter.
old-location: display\d3dddicb_queryadapterinfo.htm
old-project: display
ms.assetid: 484406a5-54be-49fa-839a-2e55747020f4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDICB_QUERYADAPTERINFO, D3DDDICB_QUERYADAPTERINFO structure [Display Devices], D3D_param_Structs_24ed4d09-d2ff-4b79-95fc-5a1c7d146faa.xml, _D3DDDICB_QUERYADAPTERINFO, d3dumddi/D3DDDICB_QUERYADAPTERINFO, display.d3dddicb_queryadapterinfo
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
-	D3DDDICB_QUERYADAPTERINFO
product: Windows
targetos: Windows
req.typenames: D3DDDICB_QUERYADAPTERINFO
---

# _D3DDDICB_QUERYADAPTERINFO structure


## -description


The D3DDDICB_QUERYADAPTERINFO structure contains information that describes the graphics adapter.


## -syntax


````
typedef struct _D3DDDICB_QUERYADAPTERINFO {
  VOID *pPrivateDriverData;
  UINT PrivateDriverDataSize;
} D3DDDICB_QUERYADAPTERINFO;
````


## -struct-fields




### -field pPrivateDriverData

[out] A pointer to a buffer that the display miniport driver can fill with information about the graphics adapter.


### -field PrivateDriverDataSize

[in/out] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md">pfnQueryAdapterInfoCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_QUERYADAPTERINFO structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

