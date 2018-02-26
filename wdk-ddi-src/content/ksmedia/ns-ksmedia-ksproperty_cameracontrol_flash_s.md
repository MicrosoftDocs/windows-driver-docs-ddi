---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_FLASH_S
title: KSPROPERTY_CAMERACONTROL_FLASH_S
author: windows-driver-content
description: Describes flash control properties in the PROPSETID_VIDCAP_CAMERACONTROL_FLASH camera control property set. This structure specifies property values that are used by applications to configure the camera's flash.
old-location: stream\ksproperty_cameracontrol_flash_s.htm
old-project: stream
ms.assetid: 5d02c019-9a4a-458a-8361-7597bb1fe1a2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PKSPROPERTY_CAMERACONTROL_FLASH_S, ,, A, C, E, F, H, K, KSPROPERTY_CAMERACONTROL_FLASH_AUTO, KSPROPERTY_CAMERACONTROL_FLASH_FLAGS_AUTO, KSPROPERTY_CAMERACONTROL_FLASH_FLAGS_MANUAL, KSPROPERTY_CAMERACONTROL_FLASH_OFF, KSPROPERTY_CAMERACONTROL_FLASH_ON, KSPROPERTY_CAMERACONTROL_FLASH_S, KSPROPERTY_CAMERACONTROL_FLASH_S structure [Streaming Media Devices], L, M, N, O, P, PKSPROPERTY_CAMERACONTROL_FLASH_S, PKSPROPERTY_CAMERACONTROL_FLASH_S structure pointer [Streaming Media Devices], R, S, T, Y, _, ksmedia/KSPROPERTY_CAMERACONTROL_FLASH_S, ksmedia/PKSPROPERTY_CAMERACONTROL_FLASH_S, stream.ksproperty_cameracontrol_flash_s"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksmedia.h
apiname:
-	KSPROPERTY_CAMERACONTROL_FLASH_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_FLASH_S, *PKSPROPERTY_CAMERACONTROL_FLASH_S
---

# KSPROPERTY_CAMERACONTROL_FLASH_S structure


## -description


Describes flash control properties in the <b>PROPSETID_VIDCAP_CAMERACONTROL_FLASH</b> camera control property set. This structure specifies property values that are used by applications to configure the camera's flash.


## -syntax


````
typedef struct {
  ULONG Flash;
  ULONG Capabilities;
} KSPROPERTY_CAMERACONTROL_FLASH_S, *PKSPROPERTY_CAMERACONTROL_FLASH_S;
````


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_CAMERACONTROL_FLASH_S structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

