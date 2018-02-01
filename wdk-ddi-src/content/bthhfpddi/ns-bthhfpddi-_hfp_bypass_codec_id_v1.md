---
UID: NS:bthhfpddi._HFP_BYPASS_CODEC_ID_V1
title: "_HFP_BYPASS_CODEC_ID_V1"
author: windows-driver-content
description: The HFP_BYPASS_CODEC_ID_V1 structure defines version 1 of the supported codec ID structure.
old-location: audio\hfp_bypass_codec_id_v1.htm
old-project: audio
ms.assetid: FB618271-A1E9-4F47-97DC-F4ACAA01028C
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: HFP_BYPASS_CODEC_ID_V1, bthhfpddi/PHFP_BYPASS_CODEC_ID_V1, bthhfpddi/HFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1 structure [Audio Devices], PHFP_BYPASS_CODEC_ID_V1 structure pointer [Audio Devices], _HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1, audio.hfp_bypass_codec_id_v1, PHFP_BYPASS_CODEC_ID_V1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthhfpddi.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bthhfpddi.h
apiname:
-	HFP_BYPASS_CODEC_ID_V1
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1
---

# _HFP_BYPASS_CODEC_ID_V1 structure


## -description


The HFP_BYPASS_CODEC_ID_V1 structure defines version 1 of the supported codec ID structure.


## -syntax


````
typedef struct _HFP_BYPASS_CODEC_ID_V1 {
  UCHAR CodecId;
} HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1;
````


## -struct-fields




### -field CodecId

The codec ID can be any of the values in the following table.
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0</td>
<td>Undefined codec</td>
</tr>
<tr>
<td>1</td>
<td>CVSD codec (narrow band) </td>
</tr>
<tr>
<td>2</td>
<td>mSBC codec (wide band speech)</td>
</tr>
</table> 


## -see-also

<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_codec_id.md">IOCTL_BTHHFP_DEVICE_GET_CODEC_ID</a>

<a href="..\bthhfpddi\ne-bthhfpddi-_hfp_bypass_codec_id_version.md">HFP_BYPASS_CODEC_ID_VERSION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HFP_BYPASS_CODEC_ID_V1 structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

