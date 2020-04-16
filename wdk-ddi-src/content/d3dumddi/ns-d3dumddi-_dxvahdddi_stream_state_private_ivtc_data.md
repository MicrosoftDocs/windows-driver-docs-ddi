---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA
title: _DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA (d3dumddi.h)
description: The DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA structure describes private stream-state data that is used to query the inverse telecine statistics from the driver.
old-location: display\dxvahdddi_stream_state_private_ivtc_data.htm
tech.root: display
ms.assetid: d882a13e-cc07-4e82-857e-499bc397517e
ms.date: 05/10/2018
keywords: ["_DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA structure"]
ms.keywords: DXVA2_Structs_f5928683-1553-42e0-a36e-86ff64301b45.xml, DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA, DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA, display.dxvahdddi_stream_state_private_ivtc_data
f1_keywords:
 - "d3dumddi/DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA is supported beginning with the Windows 7 operating system.
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
- DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA
---

# _DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA structure describes private stream-state data that is used to query the inverse telecine statistics from the driver. 


## -struct-fields




### -field Enable

[in/out] A Boolean value that indicates whether to capture the statistics is enabled. By enabling the capture of statistics, the driver resets all the statistics data to zero. The default value is <b>FALSE</b>, which indicates that capturing the statistics is disabled. 


### -field ITelecineFlags

[out] One of the following DXVAHDDDI_ITELECINE_CAPS enumeration values that indicates the telecine type that the driver detected while reversing the telecined frames.

| **Value** | **Meaning** | 
|:--|:--|
| DXVAHDDDI_ITELECINE_CAPS_32 (0x1) | The driver can perform reverse 3:2 telecine, NTSC(60i) -> Film(24p). | 
| DXVAHDDDI_ITELECINE_CAPS_22 (0x2) | The driver can perform reverse 2:2 telecine, PAL(50i) -> Film(25p:4% faster) and NTSC(60i) -> CG(30p). | 
| DXVAHDDDI_ITELECINE_CAPS_2224 (0x4) | The driver can perform reverse 2:2:2:4 telecine, NTSC(60i) -> DVCAM(24p). | 
| DXVAHDDDI_ITELECINE_CAPS_2332 (0x8) | The driver can perform reverse 2:3:3:2 telecine, NTSC(60i) -> DVCAM(24p). | 
| DXVAHDDDI_ITELECINE_CAPS_32322 (0x10) | The driver can perform reverse 3:2:3:2:2 telecine, NTSC(60i) -> Film(25p:4% faster). | 
| DXVAHDDDI_ITELECINE_CAPS_55 (0x20) | The driver can perform reverse 5:5 telecine, NTSC(60i) -> Animation(12p). | 
| DXVAHDDDI_ITELECINE_CAPS_64 (0x40) | The driver can perform reverse 6:4 telecine, NTSC(60i) -> Animation(12p). | 
| DXVAHDDDI_ITELECINE_CAPS_87 (0x80) | The driver can perform reverse 8:7 telecine, NTSC(60i) -> Anime(8p). | 
| DXVAHDDDI_ITELECINE_CAPS_222222222223 (0x100) | The driver can perform reverse 2:2:2:2:2:2:2:2:2:2:2:3 telecine, PAL(50i) -> Film(24p). | 
| DXVAHDDDI_ITELECINE_CAPS_OTHER (0x80000000) | The driver can perform reverse non-standard telecine. | 



### -field Frames

[out] The number of consecutive frames that the driver detects for the telecined frames. 


### -field InputField

[out] The last field number of the input stream that was processed (so far). The driver updates this member after the driver has processed the input field that is specified in the <b>InputFrameOrField</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_data">DXVAHDDDI_STREAM_DATA</a> structure. 


## -remarks



The DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC GUID is set in the <b>Guid</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_private_data">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a> structure when the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_getvideoprocessstreamstateprivate">GetVideoProcessStreamStatePrivate</a> function is called to query the inverse telecine statistics from the driver.

When an application de-interlaces an interlaced stream, the driver might inverse the telecined frames. If the driver supports inverse telecine statistics, the application can query the statistics data.

The playback application can dynamically switch the frame rate converter as described in the following scenario:

<ul>
<li>
The application enables the inverse telecine statistics. 

</li>
<li>
The application begins to de-interlace the interlaced fields to the progressive frames. 

</li>
<li>
At some point, the application queries the statistics and determines the streams are telecined frames.

</li>
<li>
The application enables the custom frame rate in order to output the frames at the original content frame rate (for example, 60i -> 24p). 

</li>
</ul>
The application continues to query the statistics to determine if the frames are changed (for example, progressive or interlaced).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_data">DXVAHDDDI_STREAM_DATA</a>
 

 

