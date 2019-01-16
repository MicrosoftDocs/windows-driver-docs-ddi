---
UID: NS:ksmedia.__unnamed_struct_120
title: KSPROPERTY_CAMERACONTROL_FLASH_S
description: Describes flash control properties in the PROPSETID_VIDCAP_CAMERACONTROL_FLASH camera control property set. This structure specifies property values that are used by applications to configure the camera's flash.
old-location: stream\ksproperty_cameracontrol_flash_s.htm
tech.root: stream
ms.assetid: 5d02c019-9a4a-458a-8361-7597bb1fe1a2
ms.date: 04/23/2018
ms.keywords: "*PKSPROPERTY_CAMERACONTROL_FLASH_S, KSPROPERTY_CAMERACONTROL_FLASH_AUTO, KSPROPERTY_CAMERACONTROL_FLASH_FLAGS_AUTO, KSPROPERTY_CAMERACONTROL_FLASH_FLAGS_MANUAL, KSPROPERTY_CAMERACONTROL_FLASH_OFF, KSPROPERTY_CAMERACONTROL_FLASH_ON, KSPROPERTY_CAMERACONTROL_FLASH_S, KSPROPERTY_CAMERACONTROL_FLASH_S structure [Streaming Media Devices], PKSPROPERTY_CAMERACONTROL_FLASH_S, PKSPROPERTY_CAMERACONTROL_FLASH_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_FLASH_S, ksmedia/PKSPROPERTY_CAMERACONTROL_FLASH_S, stream.ksproperty_cameracontrol_flash_s"
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	Ksmedia.h
api_name:
-	KSPROPERTY_CAMERACONTROL_FLASH_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_FLASH_S, *PKSPROPERTY_CAMERACONTROL_FLASH_S
---

# KSPROPERTY_CAMERACONTROL_FLASH_S structure


## -description


Describes flash control properties in the <b>PROPSETID_VIDCAP_CAMERACONTROL_FLASH</b> camera control property set. This structure specifies property values that are used by applications to configure the camera's flash.


## -struct-fields




### -field Flash

Indicates requested flash settings. This value must be one of these possible values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_FLASH_OFF"></a><a id="ksproperty_cameracontrol_flash_off"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_FLASH_OFF</b></dt>
</dl>
</td>
<td width="60%">
The flash should never activate.

</td>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_FLASH_ON"></a><a id="ksproperty_cameracontrol_flash_on"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_FLASH_ON</b></dt>
</dl>
</td>
<td width="60%">
The flash should activate regardless of lighting conditions.

</td>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_FLASH_AUTO"></a><a id="ksproperty_cameracontrol_flash_auto"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_FLASH_AUTO</b></dt>
</dl>
</td>
<td width="60%">
The flash should be controlled by the device and driver based on lighting conditions.

</td>
</tr>
</table>
 


### -field Capabilities

Indicates the flash modes that the device supports. This value is a bitwise <b>OR</b> of these possible values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_FLASH_FLAGS_AUTO"></a><a id="ksproperty_cameracontrol_flash_flags_auto"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_FLASH_FLAGS_AUTO</b></dt>
</dl>
</td>
<td width="60%">
The device and driver automatically control flash settings.

</td>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_FLASH_FLAGS_MANUAL"></a><a id="ksproperty_cameracontrol_flash_flags_manual"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_FLASH_FLAGS_MANUAL</b></dt>
</dl>
</td>
<td width="60%">
The user manually sets the flash settings.

</td>
</tr>
</table>
 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj156041">KSPROPERTY_CAMERACONTROL_FLASH_PROPERTY</a>
 

 

