---
UID: NS:d3dumddi._D3DDDIARG_CREATELIGHT
title: "_D3DDDIARG_CREATELIGHT"
author: windows-driver-content
description: The D3DDDIARG_CREATELIGHT structure contains the index into the light array.
old-location: display\d3dddiarg_createlight.htm
old-project: display
ms.assetid: 14dcff4a-3295-435b-a1b2-f3aa15117673
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIARG_CREATELIGHT structure [Display Devices], UMDisplayDriver_param_Structs_683ae423-2e77-49e2-8028-3980a2f1a32d.xml, d3dumddi/D3DDDIARG_CREATELIGHT, D3DDDIARG_CREATELIGHT, display.d3dddiarg_createlight, _D3DDDIARG_CREATELIGHT
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
-	D3DDDIARG_CREATELIGHT
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATELIGHT
---

# _D3DDDIARG_CREATELIGHT structure


## -description


The D3DDDIARG_CREATELIGHT structure contains the index into the light array.


## -syntax


````
typedef struct _D3DDDIARG_CREATELIGHT {
  UINT Index;
} D3DDDIARG_CREATELIGHT;
````


## -struct-fields




### -field Index

[in] The index of the light to create.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createlight.md">CreateLight</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CREATELIGHT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

