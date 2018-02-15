---
UID: NS:d3dumddi._D3DDDIARG_GETCAPS
title: "_D3DDDIARG_GETCAPS"
author: windows-driver-content
description: The D3DDDIARG_GETCAPS structure contains display device capabilities of a particular type.
old-location: display\d3dddiarg_getcaps.htm
old-project: display
ms.assetid: 50063bd0-c9d4-4013-8f83-8f9d92aa87c0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DDDIARG_GETCAPS, D3DDDIARG_GETCAPS structure [Display Devices], d3dumddi/D3DDDIARG_GETCAPS, D3DDDIARG_GETCAPS, display.d3dddiarg_getcaps, UMDisplayDriver_param_Structs_05260c15-4f63-4a85-b9c8-db53ed8135cd.xml"
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
-	D3DDDIARG_GETCAPS
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETCAPS
---

# _D3DDDIARG_GETCAPS structure


## -description


The D3DDDIARG_GETCAPS structure contains display device capabilities of a particular type.


## -syntax


````
typedef struct _D3DDDIARG_GETCAPS {
  D3DDDICAPS_TYPE Type;
  VOID            *pInfo;
  VOID            *pData;
  UINT            DataSize;
} D3DDDIARG_GETCAPS;
````


## -struct-fields




### -field Type

[in] The type of capabilities to retrieve. The Microsoft Direct3D runtime can supply one of the values from the <a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a> enumeration type, possibly along with information in the buffer that is pointed to by <b>pInfo</b>, to retrieve particular capability data in the buffer at <b>pData</b>.


### -field pInfo

[in] A pointer to a buffer that contains data that specifies the specific condition on which to retrieve the capabilities of the type that is specified by the <b>Type</b> member.


### -field pData

[out] A pointer to a buffer that is filled with capabilities of the type that is specified by the <b>Type</b> member and possibly determined by the condition that is specified in the buffer at <b>pInfo</b>.


### -field DataSize

[in/out] The size, in bytes, of the buffer at <b>pData</b>.


## -remarks



For information on how to specify <b>D3DDDIARG_GETCAPS</b> member values along with <a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a> constant values, see Remarks of <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>.




## -see-also

<a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_GETCAPS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

