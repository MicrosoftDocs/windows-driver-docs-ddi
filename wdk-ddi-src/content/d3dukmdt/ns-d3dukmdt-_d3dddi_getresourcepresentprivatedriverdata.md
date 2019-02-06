---
UID: NS:d3dukmdt._D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA
title: _D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA (d3dukmdt.h)
description: D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA is used with pfnGetResourcePresentPrivateDriverDataCb to query the resource private data, which is associated with the resource during Present.
old-location: display\d3dddi_getresourcepresentprivatedriverdata.htm
tech.root: display
ms.assetid: 4473E808-D22E-47C4-8619-7427C8BA682E
ms.date: 05/10/2018
ms.keywords: D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA, D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA structure [Display Devices], _D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA, d3dukmdt/D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA, display.d3dddi_getresourcepresentprivatedriverdata
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dukmdt.h
api_name:
-	D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA
---

# _D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA structure


## -description


<b>D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA</b> is used with <a href="https://msdn.microsoft.com/D4F0F272-60DC-4060-9762-3DB49236CE62">pfnGetResourcePresentPrivateDriverDataCb</a> to query the resource private data, which is associated with the resource during Present. 



## -struct-fields




### -field hResource

[in] A DirectX graphics kernel resource handle. 



### -field PrivateDriverDataSize

[in, out] The size of the <b>pPrivateDriverData</b> buffer in bytes. When zero or when there is insufficient space, the size of the required buffer is returned back to the caller along with a <b>STATUS_INVALID_BUFFER_SIZE</b><b>HRESULT</b> value from the calling method. 

<div class="alert"><b>Note</b>  By the time another call is made with the new buffer size, the resource could be associated with a different sized buffer.</div>
<div> </div>

### -field pPrivateDriverData

[in, out] The buffer where the private data will be written to. 



## -see-also




<a href="https://msdn.microsoft.com/D4F0F272-60DC-4060-9762-3DB49236CE62">pfnGetResourcePresentPrivateDriverDataCb</a>
 

 

