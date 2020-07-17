---
UID: NS:ksmedia.__unnamed_struct_106
title: KSPROPERTY_TUNER_SCAN_CAPS_S (ksmedia.h)
description: The KSPROPERTY_TUNER_SCAN_CAPS_S structure describes the hardware scanning capabilities of a tuning device.
old-location: stream\ksproperty_tuner_scan_caps_s.htm
tech.root: stream
ms.assetid: 5f05b24b-cf46-4302-a445-a9df029661cd
ms.date: 04/30/2019
keywords: ["KSPROPERTY_TUNER_SCAN_CAPS_S structure"]
ms.keywords: "*PKSPROPERTY_TUNER_SCAN_CAPS_S, KSPROPERTY_TUNER_SCAN_CAPS_S, KSPROPERTY_TUNER_SCAN_CAPS_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_SCAN_CAPS_S, PKSPROPERTY_TUNER_SCAN_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_SCAN_CAPS_S, ksmedia/PKSPROPERTY_TUNER_SCAN_CAPS_S, stream.ksproperty_tuner_scan_caps_s, vidcapstruct_fbbea2b1-4a4d-40f0-b988-4ffab19155f5.xml"
f1_keywords:
 - "ksmedia/KSPROPERTY_TUNER_SCAN_CAPS_S"
 - "KSPROPERTY_TUNER_SCAN_CAPS_S"
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
- KSPROPERTY_TUNER_SCAN_CAPS_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_SCAN_CAPS_S, *PKSPROPERTY_TUNER_SCAN_CAPS_S
---

# KSPROPERTY_TUNER_SCAN_CAPS_S structure


## -description


The KSPROPERTY_TUNER_SCAN_CAPS_S structure describes the hardware scanning capabilities of a tuning device.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field fSupportsHardwareAssistedScanning

A Boolean value that indicates whether the driver or firmware for a tuner supports hardware-assisted scanning operations. <b>TRUE</b> indicates that the driver or firmware for a tuner supports hardware-assisted scanning operations. <b>FALSE</b> indicates that the driver or firmware does not support hardware-assisted scanning operations. 


### -field SupportedBroadcastStandards

The number of broadcast video standard types that the tuning device can support. A hybrid tuner can support multiple types. 


### -field GUIDBucket

An array of GUIDs for the network types that the tuning device supports. 

Based on the supported number in <b>SupportedBroadcastStandards</b> that is returned in the initial call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-scan-caps">KSPROPERTY_TUNER_SCAN_CAPS</a> property, the analog or digital tuner filter then allocates an array of GUIDs. The driver uses this allocated user buffer to return all the supported GUIDs in the next call to KSPROPERTY_TUNER_SCAN_CAPS. The driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-probeforwrite">ProbeForWrite</a> function to validate this user buffer and must ensure that the length of the buffer is valid. Although unlikely, if the driver will access this buffer in an arbitrary thread, it should map the buffer into kernel space. Currently, scanning capabilities are defined for supporting the analog standard. If the driver supports analog and the application intends to start a scanning session for analog, the corresponding capabilities are defined by the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-networktype-scan-caps">KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS</a> property. Other scanning capabilities to support other broadcast standards (for example, DVB-S) are not yet supported. 


### -field lengthofBucket

The number of GUIDs in the <b>GUIDBucket</b> array. 


## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-networktype-scan-caps">KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-scan-caps">KSPROPERTY_TUNER_SCAN_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/propsetid-tuner">PROPSETID_TUNER</a>
 

 

