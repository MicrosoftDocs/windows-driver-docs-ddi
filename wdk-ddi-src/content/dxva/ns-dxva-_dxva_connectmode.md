---
UID: NS:dxva._DXVA_ConnectMode
title: _DXVA_ConnectMode (dxva.h)
description: The DXVA_ConnectMode structure is sent by the host decoder to the accelerator to define the restricted profile used within a DirectX VA connection.
old-location: display\dxva_connectmode.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXVA_ConnectMode structure"]
ms.keywords: "*LPDXVA_ConnectMode, DXVA_ConnectMode, DXVA_ConnectMode structure [Display Devices], LPDXVA_ConnectMode, LPDXVA_ConnectMode structure pointer [Display Devices], _DXVA_ConnectMode, display.dxva_connectmode, dxva/DXVA_ConnectMode, dxva/LPDXVA_ConnectMode, dxvaref_24815d94-550d-4b5c-be95-2fb0882781c0.xml"
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: DXVA_ConnectMode, *LPDXVA_ConnectMode
f1_keywords:
 - _DXVA_ConnectMode
 - dxva/_DXVA_ConnectMode
 - LPDXVA_ConnectMode
 - dxva/LPDXVA_ConnectMode
 - DXVA_ConnectMode
 - dxva/DXVA_ConnectMode
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - _DXVA_ConnectMode
 - LPDXVA_ConnectMode
 - DXVA_ConnectMode
---

# _DXVA_ConnectMode structure


## -description

The DXVA_ConnectMode structure is sent by the host decoder to the accelerator to define the restricted profile used within a DirectX VA connection.

## -struct-fields

### -field guidMode

Specifies the GUID associated with the <a href="/windows-hardware/drivers/display/restricted-profiles">restricted profile</a> to be used.

### -field wRestrictedMode

Specifies the numeric identifier of the restricted profile to be used.

## -remarks

The following GUIDs placed in the <b>guidMode</b> member of this structure set the <a href="/windows-hardware/drivers/display/restricted-profiles">restricted profile</a> to be used. The constants that define the GUIDs used are in <i>dxva.h</i>.

| **GUID Name** | **Restricted Profile Used** | 
|:--|:--|
| DXVA_ModeNone | Nonrestricted | 
| DXVA_ModeH261_A | [H261_A](/windows-hardware/drivers/display/h261-a)  | 
| DXVA_ModeH261_B | [H261_B](/windows-hardware/drivers/display/h261-b)  | 
| DXVA_ModeH263_A | [H263_A](/windows-hardware/drivers/display/h263-a)  | 
| DXVA_ModeH263_B | [H263_B](/windows-hardware/drivers/display/h263-b)  | 
| DXVA_ModeH263_C | [H263_C](/windows-hardware/drivers/display/h263-c)  | 
| DXVA_ModeH263_D | [H263_D](/windows-hardware/drivers/display/h263-d)  | 
| DXVA_ModeH263_E | [H263_E](/windows-hardware/drivers/display/h263-e)  | 
| DXVA_ModeH263_F | [H263_F](/windows-hardware/drivers/display/h263-f)  | 
| DXVA_ModeMPEG1_A | [MPEG1_A](/windows-hardware/drivers/display/mpeg1-a)  | 
| DXVA_ModeMPEG2_A | [MPEG2_A](/windows-hardware/drivers/display/mpeg2-a)  | 
| DXVA_ModeMPEG2_B | [MPEG2_B](/windows-hardware/drivers/display/mpeg2-b)  | 
| DXVA_ModeMPEG2_C | [MPEG2_C](/windows-hardware/drivers/display/mpeg2-c)  | 
| DXVA_ModeMPEG2_D | [MPEG2_D](/windows-hardware/drivers/display/mpeg2-d)  | 
| DXVA_ModeH264_A | H264_A | 
| DXVA_ModeH264_B | H264_B | 
| DXVA_ModeH264_C | H264_C | 
| DXVA_ModeH264_D | H264_D | 
| DXVA_ModeH264_E | H264_E | 
| DXVA_ModeH264_F | H264_F | 
| DXVA_ModeWMV8_A | [WMV8_A](/windows-hardware/drivers/display/wmv8-a--wmv8-b--wmv9-a--wmv9-b--and-wmv9-c)  | 
| DXVA_ModeWMV8_B | [WMV8_B](/windows-hardware/drivers/display/wmv8-a--wmv8-b--wmv9-a--wmv9-b--and-wmv9-c)  | 
| DXVA_ModeWMV9_A | [WMV9_A](/windows-hardware/drivers/display/wmv8-a--wmv8-b--wmv9-a--wmv9-b--and-wmv9-c)  | 
| DXVA_ModeWMV9_B | [WMV9_B](/windows-hardware/drivers/display/wmv8-a--wmv8-b--wmv9-a--wmv9-b--and-wmv9-c)  | 
| DXVA_ModeWMV9_C | [WMV9_C](/windows-hardware/drivers/display/wmv8-a--wmv8-b--wmv9-a--wmv9-b--and-wmv9-c)  | 
| DXVA_ModeVC1_A | VC1_A | 
| DXVA_ModeVC1_B | VC1_B | 
| DXVA_ModeVC1_C | VC1_C | 
| DXVA_ModeVC1_D | VC1_D | 

The following restricted mode identifiers placed in the <b>wRestrictedMode</b> member of this structure indicate which restricted profile is used. These identifiers are defined in <i>dxva.h</i>.

| **Restricted Mode Identifier** | **Restricted Profile Used** | 
|:--|:--|
| DXVA_RESTRICTED_MODE_UNRESTRICTED | Nonrestricted | 
| DXVA_RESTRICTED_MODE_H261_A | [H261_A](/windows-hardware/drivers/display/h261-a)  | 
| DXVA_RESTRICTED_MODE_H261_B | [H261_B](/windows-hardware/drivers/display/h261-b)  | 
| DXVA_RESTRICTED_MODE_H263_A | [H263_A](/windows-hardware/drivers/display/h263-a)  | 
| DXVA_RESTRICTED_MODE_H263_B | [H263_B](/windows-hardware/drivers/display/h263-b)  | 
| DXVA_RESTRICTED_MODE_H263_C | [H263_C](/windows-hardware/drivers/display/h263-c)  | 
| DXVA_RESTRICTED_MODE_H263_D | [H263_D](/windows-hardware/drivers/display/h263-d)  | 
| DXVA_RESTRICTED_MODE_H263_E | [H263_E](/windows-hardware/drivers/display/h263-e)  | 
| DXVA_RESTRICTED_MODE_H263_F | [H263_F](/windows-hardware/drivers/display/h263-f)  | 
| DXVA_RESTRICTED_MODE_MPEG1_A | [MPEG1_A](/windows-hardware/drivers/display/mpeg1-a)  | 
| DXVA_RESTRICTED_MODE_MPEG2_A | [MPEG2_A](/windows-hardware/drivers/display/mpeg2-a)  | 
| DXVA_RESTRICTED_MODE_MPEG2_B | [MPEG2_B](/windows-hardware/drivers/display/mpeg2-b)  | 
| DXVA_RESTRICTED_MODE_MPEG2_C | [MPEG2_C](/windows-hardware/drivers/display/mpeg2-c)  | 
| DXVA_RESTRICTED_MODE_MPEG2_D | [MPEG2_D](/windows-hardware/drivers/display/mpeg2-d)  | 
| DXVA_RESTRICTED_MODE_H264_A | H264_A | 
| DXVA_RESTRICTED_MODE_H264_B | H264_B | 
| DXVA_RESTRICTED_MODE_H264_C | H264_C | 
| DXVA_RESTRICTED_MODE_H264_D | H264_D | 
| DXVA_RESTRICTED_MODE_H264_E | H264_E | 
| DXVA_RESTRICTED_MODE_H264_F | H264_F | 
| DXVA_RESTRICTED_MODE_WMV8_A | [WMV8_A](/windows-hardware/drivers/display/wmv8-a--wmv8-b--wmv9-a--wmv9-b--and-wmv9-c)  | 
| DXVA_RESTRICTED_MODE_WMV8_B | [WMV8_B](/windows-hardware/drivers/display/wmv8-a--wmv8-b--wmv9-a--wmv9-b--and-wmv9-c)  | 
| DXVA_RESTRICTED_MODE_WMV9_A | [WMV9_A](/windows-hardware/drivers/display/wmv8-a--wmv8-b--wmv9-a--wmv9-b--and-wmv9-c)  | 
| DXVA_RESTRICTED_MODE_WMV9_B | [WMV9_B](/windows-hardware/drivers/display/wmv8-a--wmv8-b--wmv9-a--wmv9-b--and-wmv9-c)  | 
| DXVA_RESTRICTED_MODE_WMV9_C | [WMV9_C](/windows-hardware/drivers/display/wmv8-a--wmv8-b--wmv9-a--wmv9-b--and-wmv9-c)  | 
| DXVA_RESTRICTED_MODE_VC1_A | VC1_A | 
| DXVA_RESTRICTED_MODE_VC1_B | VC1_B | 
| DXVA_RESTRICTED_MODE_VC1_C | VC1_C | 
| DXVA_RESTRICTED_MODE_VC1_D | VC1_D | 

 

For information about the restricted profiles of the MPEG-4 AVC (H.264) and VC-1 video codec standards, download <a href="https://go.microsoft.com/fwlink/p/?linkid=141799">DirectX Video Acceleration Specification for H.264/AVC Decoding</a> and <a href="https://go.microsoft.com/fwlink/p/?linkid=141800">DirectX Video Acceleration Specification for Windows Media Video v8, v9 and vA Decoding (Including SMPTE 421M "VC-1")</a>.

