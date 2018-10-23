---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA
title: "_DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA"
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA structure describes stream-state data that specifies the luma key of the input. The driver assumes that a pixel that has a luma value within the luma-key range is transparent.
old-location: display\dxvahdddi_stream_state_luma_key_data.htm
tech.root: display
ms.assetid: bd620f6d-6c19-41d4-a68c-3dcf2eec93ae
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_a76427d8-e062-4fae-9350-f68d162effef.xml, DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA, DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA, display.dxvahdddi_stream_state_luma_key_data
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA
---

# _DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA structure describes stream-state data that specifies the luma key of the input. The driver assumes that a pixel that has a luma value within the luma-key range is transparent. 


## -struct-fields




### -field Enable

[in] A Boolean value that specifies whether the luma key is enabled. The default value is <b>FALSE</b>, which indicates that the luma key is disabled. 


### -field Lower

[in] A FLOAT value in the 0.0 to 1.0 range that describes the lower luma-key value. The default value is 0.0. 


### -field Upper

[in] A FLOAT value in the 0.0 to 1.0 range that describes the upper luma-key value. The default value is 0.0. 


## -remarks



The Direct3D runtime specifies the DXVAHDDDI_STREAM_STATE_LUMA_KEY state in the <b>State</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543098">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a> structure in a call to the driver's <a href="https://msdn.microsoft.com/b48fbe58-056a-4c3b-8e1e-c65515c21ee4">SetVideoProcessStreamState</a> function. This happens  only when the driver has previously set the DXVAHDDDI_FEATURE_CAPS_LUMA_KEY value in the <b>FeatureCaps</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set. 

If the driver does not set the DXVAHDDDI_INPUT_FORMAT_CAPS_RGB_LUMA_KEY value in the <b>InputFormatCaps</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set, the driver ignores the luma-key data.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543098">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>



<a href="https://msdn.microsoft.com/b48fbe58-056a-4c3b-8e1e-c65515c21ee4">SetVideoProcessStreamState</a>
 

 

