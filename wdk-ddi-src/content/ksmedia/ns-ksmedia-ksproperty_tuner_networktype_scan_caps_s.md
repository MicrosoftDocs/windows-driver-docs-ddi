---
UID: NS:ksmedia.KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S
title: KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure describes the scanning capabilities of a broadcast network type that a tuning device supports.
old-location: stream\ksproperty_tuner_networktype_scan_caps_s.htm
old-project: stream
ms.assetid: e6fe9278-d34e-4fba-80f9-84d6ededbfc1
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "*PKSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S, vidcapstruct_7ffc22b0-3a65-449e-a0cb-6816a99738d6.xml, ksmedia/PKSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S, KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S, stream.ksproperty_tuner_networktype_scan_caps_s, PKSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S, PKSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S, KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure [Streaming Media Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S, *PKSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S
---

# KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure


## -description


The KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure describes the scanning capabilities of a broadcast network type that a tuning device supports.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  GUID       NetworkType;
  ULONG      BufferSize;
  PVOID      NetworkTunerCapabilities;
} KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S, *PKSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field NetworkType

A GUID for the broadcast network type for which the tuner filter receives capabilities. The driver returned this GUID as an element in the array that the <b>GUIDBucket</b> member of the <a href="..\ksmedia\ns-ksmedia-ksproperty_tuner_scan_caps_s.md">KSPROPERTY_TUNER_SCAN_CAPS_S</a> structure specifies in a call to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff565887">KSPROPERTY_TUNER_SCAN_CAPS</a> property. 


### -field BufferSize

The size, in bytes, of the buffer that is required to hold the network capabilities and that the <b>NetworkTunerCapabilities</b> member points to. 


### -field NetworkTunerCapabilities

A pointer to a buffer to hold the scanning capabilities of a broadcast network type. For example, if the ANALOG_TV_NETWORK_TYPE GUID is set in the <b>NetworkType</b> member, the driver fills the buffer with a populated <a href="..\ksmedia\ns-ksmedia-tuner_analog_caps_s.md">TUNER_ANALOG_CAPS_S</a> structure. 


## -see-also

<a href="..\ksmedia\ns-ksmedia-ksproperty_tuner_scan_caps_s.md">KSPROPERTY_TUNER_SCAN_CAPS_S</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565881">KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS</a>

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="..\ksmedia\ns-ksmedia-tuner_analog_caps_s.md">TUNER_ANALOG_CAPS_S</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565887">KSPROPERTY_TUNER_SCAN_CAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

