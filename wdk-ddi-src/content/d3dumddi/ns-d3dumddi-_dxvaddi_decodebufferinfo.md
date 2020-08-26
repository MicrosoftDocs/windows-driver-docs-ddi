---
UID: NS:d3dumddi._DXVADDI_DECODEBUFFERINFO
title: _DXVADDI_DECODEBUFFERINFO (d3dumddi.h)
description: The DXVADDI_DECODEBUFFERINFO structure describes information about a particular type of compressed buffer that is required for a video decoding scenario.
old-location: display\dxvaddi_decodebufferinfo.htm
tech.root: display
ms.assetid: e0a0ad31-86c1-44bd-b069-70442973a539
ms.date: 05/10/2018
keywords: ["DXVADDI_DECODEBUFFERINFO structure"]
ms.keywords: DXVA2_Structs_b076dffc-bfe0-4141-a075-9349b69af16c.xml, DXVADDI_DECODEBUFFERINFO, DXVADDI_DECODEBUFFERINFO structure [Display Devices], _DXVADDI_DECODEBUFFERINFO, d3dumddi/DXVADDI_DECODEBUFFERINFO, display.dxvaddi_decodebufferinfo
f1_keywords:
 - "d3dumddi/DXVADDI_DECODEBUFFERINFO"
 - "DXVADDI_DECODEBUFFERINFO"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- DXVADDI_DECODEBUFFERINFO
targetos: Windows
req.typenames: DXVADDI_DECODEBUFFERINFO
---

# _DXVADDI_DECODEBUFFERINFO structure


## -description


The DXVADDI_DECODEBUFFERINFO structure describes information about a particular type of compressed buffer that is required for a video decoding scenario. 


## -struct-fields




### -field CompressedBufferType

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the buffer.


### -field CreationWidth

[out] The width of the data in the buffer as the number of units of bits. For example, AYUV data is specified in 32-bit units, IA44/AI44 data is specified in 8-bit units, and DPXD data is specified in 2-bit units.

The driver must assign a value to <b>CreationWidth</b> that is a multiple of 2 and does not exceed 65535.


### -field CreationHeight

[out] The height of the data in the buffer as the number of units of bits. For example, AYUV data is specified in 32-bit units, IA44/AI44 data is specified in 8-bit units, and DPXD data is specified in 2-bit units.

The driver must assign a value to <b>CreationHeight</b> that does not exceed 65535.


### -field CreationPool

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddi_pool">D3DDDI_POOL</a>-typed value that indicates the type of memory that the buffer exists in.


## -remarks



A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_decodeinput">DXVADDI_DECODEINPUT</a> structure is specified in the <b>pInfo</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a> structure--along with a D3DDDICAPS_GETDECODECOMPRESSEDBUFFERINFO value in the <b>Type</b> member of D3DDDIARG_GETCAPS--in a call to the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function to retrieve information about the types of compressed buffers that are required to accelerate a particular DirectX VA video decode type. The information about the types of compressed buffers is returned in an array of DXVADDI_DECODEBUFFERINFO structures through the <b>pData</b> member of D3DDDIARG_GETCAPS.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddicaps_type">D3DDDICAPS_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_decodeinput">DXVADDI_DECODEINPUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>
 

 

