---
UID: NS:d3dumddi._D3DDDIARG_GETCAPS
title: _D3DDDIARG_GETCAPS (d3dumddi.h)
description: The D3DDDIARG_GETCAPS structure contains display device capabilities of a particular type.
old-location: display\d3dddiarg_getcaps.htm
tech.root: display
ms.assetid: 50063bd0-c9d4-4013-8f83-8f9d92aa87c0
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_GETCAPS, D3DDDIARG_GETCAPS structure [Display Devices], UMDisplayDriver_param_Structs_05260c15-4f63-4a85-b9c8-db53ed8135cd.xml, _D3DDDIARG_GETCAPS, d3dumddi/D3DDDIARG_GETCAPS, display.d3dddiarg_getcaps
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_GETCAPS
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_GETCAPS
---

# _D3DDDIARG_GETCAPS structure


## -description


The D3DDDIARG_GETCAPS structure contains display device capabilities of a particular type.


## -struct-fields




### -field Type

[in] The type of capabilities to retrieve. The Microsoft Direct3D runtime can supply one of the values from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544132">D3DDDICAPS_TYPE</a> enumeration type, possibly along with information in the buffer that is pointed to by <b>pInfo</b>, to retrieve particular capability data in the buffer at <b>pData</b>.


### -field pInfo

[in] A pointer to a buffer that contains data that specifies the specific condition on which to retrieve the capabilities of the type that is specified by the <b>Type</b> member.


### -field pData

[out] A pointer to a buffer that is filled with capabilities of the type that is specified by the <b>Type</b> member and possibly determined by the condition that is specified in the buffer at <b>pInfo</b>.


### -field DataSize

[in/out] The size, in bytes, of the buffer at <b>pData</b>.


## -remarks



For information on how to specify <b>D3DDDIARG_GETCAPS</b> member values along with <a href="https://msdn.microsoft.com/library/windows/hardware/ff544132">D3DDDICAPS_TYPE</a> constant values, see Remarks of <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544132">D3DDDICAPS_TYPE</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>
 

 

