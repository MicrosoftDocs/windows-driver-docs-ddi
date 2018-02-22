---
UID: NS:d3dumddi._DXVADDI_DECODEBUFFERINFO
title: "_DXVADDI_DECODEBUFFERINFO"
author: windows-driver-content
description: The DXVADDI_DECODEBUFFERINFO structure describes information about a particular type of compressed buffer that is required for a video decoding scenario.
old-location: display\dxvaddi_decodebufferinfo.htm
old-project: display
ms.assetid: e0a0ad31-86c1-44bd-b069-70442973a539
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DXVADDI_DECODEBUFFERINFO structure [Display Devices], DXVA2_Structs_b076dffc-bfe0-4141-a075-9349b69af16c.xml, display.dxvaddi_decodebufferinfo, d3dumddi/DXVADDI_DECODEBUFFERINFO, DXVADDI_DECODEBUFFERINFO, _DXVADDI_DECODEBUFFERINFO
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
-	DXVADDI_DECODEBUFFERINFO
product: Windows
targetos: Windows
req.typenames: DXVADDI_DECODEBUFFERINFO
---

# _DXVADDI_DECODEBUFFERINFO structure


## -description


The DXVADDI_DECODEBUFFERINFO structure describes information about a particular type of compressed buffer that is required for a video decoding scenario. 


## -syntax


````
typedef struct _DXVADDI_DECODEBUFFERINFO {
  D3DDDIFORMAT CompressedBufferType;
  UINT         CreationWidth;
  UINT         CreationHeight;
  D3DDDI_POOL  CreationPool;
} DXVADDI_DECODEBUFFERINFO;
````


## -struct-fields




### -field CompressedBufferType

[out] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the buffer.


### -field CreationWidth

[out] The width of the data in the buffer as the number of units of bits. For example, AYUV data is specified in 32-bit units, IA44/AI44 data is specified in 8-bit units, and DPXD data is specified in 2-bit units.

The driver must assign a value to <b>CreationWidth</b> that is a multiple of 2 and does not exceed 65535.


### -field CreationHeight

[out] The height of the data in the buffer as the number of units of bits. For example, AYUV data is specified in 32-bit units, IA44/AI44 data is specified in 8-bit units, and DPXD data is specified in 2-bit units.

The driver must assign a value to <b>CreationHeight</b> that does not exceed 65535.


### -field CreationPool

[out] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_pool.md">D3DDDI_POOL</a>-typed value that indicates the type of memory that the buffer exists in.


## -remarks



A pointer to the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_decodeinput.md">DXVADDI_DECODEINPUT</a> structure is specified in the <b>pInfo</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a> structure--along with a D3DDDICAPS_GETDECODECOMPRESSEDBUFFERINFO value in the <b>Type</b> member of D3DDDIARG_GETCAPS--in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function to retrieve information about the types of compressed buffers that are required to accelerate a particular DirectX VA video decode type. The information about the types of compressed buffers is returned in an array of DXVADDI_DECODEBUFFERINFO structures through the <b>pData</b> member of D3DDDIARG_GETCAPS.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>



<a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_decodeinput.md">DXVADDI_DECODEINPUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_DECODEBUFFERINFO structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

