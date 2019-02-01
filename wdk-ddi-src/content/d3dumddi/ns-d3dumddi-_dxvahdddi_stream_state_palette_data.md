---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_PALETTE_DATA
title: _DXVAHDDDI_STREAM_STATE_PALETTE_DATA (d3dumddi.h)
description: The DXVAHDDDI_STREAM_STATE_PALETTE_DATA structure describes stream-state data that specifies the palette entries of the input.
old-location: display\dxvahdddi_stream_state_palette_data.htm
tech.root: display
ms.assetid: b71f3793-7856-4558-b205-7facf6d83a8c
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_4b156a58-d13f-4ffc-8ad0-3bdbb5dc7386.xml, DXVAHDDDI_STREAM_STATE_PALETTE_DATA, DXVAHDDDI_STREAM_STATE_PALETTE_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_PALETTE_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_PALETTE_DATA, display.dxvahdddi_stream_state_palette_data
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_PALETTE_DATA is supported beginning with the Windows 7 operating system.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	DXVAHDDDI_STREAM_STATE_PALETTE_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_PALETTE_DATA
---

# _DXVAHDDDI_STREAM_STATE_PALETTE_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_PALETTE_DATA structure describes stream-state data that specifies the palette entries of the input. 


## -struct-fields




### -field Count

[in] The number of palette entries in the array that the <b>pEntries</b> member specifies. The default value is 0. 


### -field pEntries

[in] An array of palette entries in either D3DFMT_A8R8G8B8 or "AYUV" <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">FOURCC</a> format type. <b>pEntries</b> is set to <b>NULL</b> to retrieve the number of palette entries. The default value is <b>NULL</b>. 


## -remarks



The 4-bit palletized "AYUV" FOURCC formats, "AI44", and "IA44" uses the first 16 entries.

The 8-bit palletized "AYUV" FOURCC format, "AI88", D3DFMT_A8P8, and D3DFMT_P8 formats uses the first 256 entries.

If a pixel has a palette index greater than the entries, the driver assumes that the palette entry is white with opaque alpha. Full range RGB is D3DCOLOR_ARGB(255, 255, 255, 255), and YCbCr is D3DCOLOR_AYUV(255, 235, 128, 128).

The Direct3D runtime maintains all the palette entries. However, the driver might truncate the palette entries array to the maximum entries required for the supported palletized format.

The alpha value of each entry is used for the alpha blending.

If the driver does not set the DXVAHDDDI_FEATURE_CAPS_ALPHA_PALETTE value in the <b>FeatureCaps</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set, every palette entry must have the alpha value set to opaque (0xFF); otherwise, the driver's <a href="https://msdn.microsoft.com/b48fbe58-056a-4c3b-8e1e-c65515c21ee4">SetVideoProcessStreamState</a> function returns an error.

For more information about alpha blending, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563072">DXVAHDDDI_STREAM_STATE_ALPHA_DATA</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563072">DXVAHDDDI_STREAM_STATE_ALPHA_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>



<a href="https://msdn.microsoft.com/b48fbe58-056a-4c3b-8e1e-c65515c21ee4">SetVideoProcessStreamState</a>
 

 

