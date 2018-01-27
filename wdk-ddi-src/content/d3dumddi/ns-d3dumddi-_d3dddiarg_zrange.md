---
UID: NS:d3dumddi._D3DDDIARG_ZRANGE
title: _D3DDDIARG_ZRANGE
author: windows-driver-content
description: The D3DDDIARG_ZRANGE structure specifies z-range minimum and maximum values.
old-location: display\d3dddiarg_zrange.htm
old-project: display
ms.assetid: 710683e7-f628-4baa-b485-75b481812b97
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDisplayDriver_param_Structs_e1184f4e-5bff-4bdc-bf7a-473039a66ff7.xml, display.d3dddiarg_zrange, D3DDDIARG_ZRANGE, _D3DDDIARG_ZRANGE, D3DDDIARG_ZRANGE structure [Display Devices], d3dumddi/D3DDDIARG_ZRANGE
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
-	D3DDDIARG_ZRANGE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_ZRANGE
---

# _D3DDDIARG_ZRANGE structure


## -description


The D3DDDIARG_ZRANGE structure specifies z-range minimum and maximum values.


## -syntax


````
typedef struct _D3DDDIARG_ZRANGE {
  FLOAT MinZ;
  FLOAT MaxZ;
} D3DDDIARG_ZRANGE;
````


## -struct-fields




### -field MinZ

[in] A FLOAT value that indicates the minimum z value for the range. 


### -field MaxZ

[in] A FLOAT value that indicates the maximum z value for the range. 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setzrange.md">SetZRange</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_ZRANGE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

