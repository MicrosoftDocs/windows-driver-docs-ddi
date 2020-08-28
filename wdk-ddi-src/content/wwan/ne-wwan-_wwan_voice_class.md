---
UID: NE:wwan._WWAN_VOICE_CLASS
title: _WWAN_VOICE_CLASS (wwan.h)
description: The WWAN_VOICE_CLASS enumeration lists the different types of voice classes that are supported by the MB device.
old-location: netvista\wwan_voice_class.htm
tech.root: netvista
ms.assetid: 288a7b44-b842-41f8-8ece-d14a709b0717
ms.date: 05/02/2018
keywords: ["WWAN_VOICE_CLASS enumeration"]
ms.keywords: "*PWWAN_VOICE_CLASS, PWWAN_VOICE_CLASS, PWWAN_VOICE_CLASS enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_VOICE_CLASS, WWAN_VOICE_CLASS enumeration [Network Drivers Starting with Windows Vista], WwanRef_13e9339b-e11b-416b-8335-51c950049c6e.xml, WwanVoiceClassMax, WwanVoiceClassNoVoice, WwanVoiceClassSeparateVoiceData, WwanVoiceClassSimultaneousVoiceData, WwanVoiceClassUnknown, _WWAN_VOICE_CLASS, netvista.wwan_voice_class, wwan/PWWAN_VOICE_CLASS, wwan/WWAN_VOICE_CLASS, wwan/WwanVoiceClassMax, wwan/WwanVoiceClassNoVoice, wwan/WwanVoiceClassSeparateVoiceData, wwan/WwanVoiceClassSimultaneousVoiceData, wwan/WwanVoiceClassUnknown"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.typenames: WWAN_VOICE_CLASS, *PWWAN_VOICE_CLASS
f1_keywords:
 - _WWAN_VOICE_CLASS
 - wwan/_WWAN_VOICE_CLASS
 - PWWAN_VOICE_CLASS
 - wwan/PWWAN_VOICE_CLASS
 - WWAN_VOICE_CLASS
 - wwan/WWAN_VOICE_CLASS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_VOICE_CLASS
---

# _WWAN_VOICE_CLASS enumeration


## -description

The WWAN_VOICE_CLASS enumeration lists the different types of voice classes that are supported by the
  MB device.

## -enum-fields

### -field WwanVoiceClassUnknown

The device uses an unknown method to support voice connections.

### -field WwanVoiceClassNoVoice

The device does not support voice connections.

### -field WwanVoiceClassSeparateVoiceData

The device supports separate voice and data connections.

### -field WwanVoiceClassSimultaneousVoiceData

The device supports simultaneous voice and data connections.

### -field WwanVoiceClassMax

The total number of supported cellular voice classes.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>

