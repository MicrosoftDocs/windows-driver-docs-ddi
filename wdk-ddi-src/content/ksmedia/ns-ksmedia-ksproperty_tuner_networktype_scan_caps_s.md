---
UID: NS:ksmedia.__unnamed_struct_107
title: KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S (ksmedia.h)
description: The KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure describes the scanning capabilities of a broadcast network type that a tuning device supports.
old-location: stream\ksproperty_tuner_networktype_scan_caps_s.htm
tech.root: stream
ms.assetid: e6fe9278-d34e-4fba-80f9-84d6ededbfc1
ms.date: 04/30/2019
ms.keywords: "*PKSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S, KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S, KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S, PKSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S, ksmedia/PKSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S, stream.ksproperty_tuner_networktype_scan_caps_s, vidcapstruct_7ffc22b0-3a65-449e-a0cb-6816a99738d6.xml"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the operating system.
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
- ksmedia.h
api_name:
- KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S, *PKSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S
---

# KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure


## -description


The KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure describes the scanning capabilities of a broadcast network type that a tuning device supports.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field NetworkType

A GUID for the broadcast network type for which the tuner filter receives capabilities. The driver returned this GUID as an element in the array that the <b>GUIDBucket</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_tuner_scan_caps_s">KSPROPERTY_TUNER_SCAN_CAPS_S</a> structure specifies in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-scan-caps">KSPROPERTY_TUNER_SCAN_CAPS</a> property. 


### -field BufferSize

The size, in bytes, of the buffer that is required to hold the network capabilities and that the <b>NetworkTunerCapabilities</b> member points to. 


### -field NetworkTunerCapabilities

A pointer to a buffer to hold the scanning capabilities of a broadcast network type. For example, if the ANALOG_TV_NETWORK_TYPE GUID is set in the <b>NetworkType</b> member, the driver fills the buffer with a populated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tuner_analog_caps_s">TUNER_ANALOG_CAPS_S</a> structure. 


## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-networktype-scan-caps">KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-scan-caps">KSPROPERTY_TUNER_SCAN_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_tuner_scan_caps_s">KSPROPERTY_TUNER_SCAN_CAPS_S</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tuner_analog_caps_s">TUNER_ANALOG_CAPS_S</a>
 

 

