---
UID: NS:d3dumddi._D3DDDIARG_GETCAPS
title: _D3DDDIARG_GETCAPS (d3dumddi.h)
description: The D3DDDIARG_GETCAPS structure contains display device capabilities of a particular type.
old-location: display\d3dddiarg_getcaps.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_GETCAPS structure"]
ms.keywords: D3DDDIARG_GETCAPS, D3DDDIARG_GETCAPS structure [Display Devices], UMDisplayDriver_param_Structs_05260c15-4f63-4a85-b9c8-db53ed8135cd.xml, _D3DDDIARG_GETCAPS, d3dumddi/D3DDDIARG_GETCAPS, display.d3dddiarg_getcaps
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
targetos: Windows
req.typenames: D3DDDIARG_GETCAPS
f1_keywords:
 - _D3DDDIARG_GETCAPS
 - d3dumddi/_D3DDDIARG_GETCAPS
 - D3DDDIARG_GETCAPS
 - d3dumddi/D3DDDIARG_GETCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_GETCAPS
 - D3DDDIARG_GETCAPS
---

# _D3DDDIARG_GETCAPS structure


## -description

The D3DDDIARG_GETCAPS structure contains display device capabilities of a particular type.

## -struct-fields

### -field Type [in]

The type of capabilities to retrieve. The Microsoft Direct3D runtime can supply one of the values from the <a href="/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddicaps_type">D3DDDICAPS_TYPE</a> enumeration type, possibly along with information in the buffer that is pointed to by <b>pInfo</b>, to retrieve particular capability data in the buffer at <b>pData</b>.

### -field pInfo [in]

A pointer to a buffer that contains data that specifies the specific condition on which to retrieve the capabilities of the type that is specified by the <b>Type</b> member.

### -field pData [out]

A pointer to a buffer that is filled with capabilities of the type that is specified by the <b>Type</b> member and possibly determined by the condition that is specified in the buffer at <b>pInfo</b>.

### -field DataSize [in/out]

The size, in bytes, of the buffer at <b>pData</b>.

## -remarks

For information on how to specify <b>D3DDDIARG_GETCAPS</b> member values along with <a href="/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddicaps_type">D3DDDICAPS_TYPE</a> constant values, see Remarks of <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddicaps_type">D3DDDICAPS_TYPE</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>

