---
UID: NS:ksmedia.KSPROPERTY_TUNER_SCAN_CAPS_S
title: KSPROPERTY_TUNER_SCAN_CAPS_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_SCAN_CAPS_S structure describes the hardware scanning capabilities of a tuning device.
old-location: stream\ksproperty_tuner_scan_caps_s.htm
old-project: stream
ms.assetid: 5f05b24b-cf46-4302-a445-a9df029661cd
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "*PKSPROPERTY_TUNER_SCAN_CAPS_S, ksmedia/PKSPROPERTY_TUNER_SCAN_CAPS_S, ksmedia/KSPROPERTY_TUNER_SCAN_CAPS_S, PKSPROPERTY_TUNER_SCAN_CAPS_S structure pointer [Streaming Media Devices], KSPROPERTY_TUNER_SCAN_CAPS_S structure [Streaming Media Devices], KSPROPERTY_TUNER_SCAN_CAPS_S, stream.ksproperty_tuner_scan_caps_s, PKSPROPERTY_TUNER_SCAN_CAPS_S, vidcapstruct_fbbea2b1-4a4d-40f0-b988-4ffab19155f5.xml"
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
-	KSPROPERTY_TUNER_SCAN_CAPS_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_SCAN_CAPS_S, *PKSPROPERTY_TUNER_SCAN_CAPS_S
---

# KSPROPERTY_TUNER_SCAN_CAPS_S structure


## -description


The KSPROPERTY_TUNER_SCAN_CAPS_S structure describes the hardware scanning capabilities of a tuning device.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  BOOL       fSupportsHardwareAssistedScanning;
  ULONG      SupportedBroadcastStandards;
  PVOID      GUIDBucket;
  ULONG      lengthofBucket;
} KSPROPERTY_TUNER_SCAN_CAPS_S, *PKSPROPERTY_TUNER_SCAN_CAPS_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field fSupportsHardwareAssistedScanning

A Boolean value that indicates whether the driver or firmware for a tuner supports hardware-assisted scanning operations. <b>TRUE</b> indicates that the driver or firmware for a tuner supports hardware-assisted scanning operations. <b>FALSE</b> indicates that the driver or firmware does not support hardware-assisted scanning operations. 


### -field SupportedBroadcastStandards

The number of broadcast video standard types that the tuning device can support. A hybrid tuner can support multiple types. 


### -field GUIDBucket

An array of GUIDs for the network types that the tuning device supports. 

Based on the supported number in <b>SupportedBroadcastStandards</b> that is returned in the initial call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565887">KSPROPERTY_TUNER_SCAN_CAPS</a> property, the analog or digital tuner filter then allocates an array of GUIDs. The driver uses this allocated user buffer to return all the supported GUIDs in the next call to KSPROPERTY_TUNER_SCAN_CAPS. The driver must call the <a href="..\wdm\nf-wdm-probeforwrite.md">ProbeForWrite</a> function to validate this user buffer and must ensure that the length of the buffer is valid. Although unlikely, if the driver will access this buffer in an arbitrary thread, it should map the buffer into kernel space. Currently, scanning capabilities are defined for supporting the analog standard. If the driver supports analog and the application intends to start a scanning session for analog, the corresponding capabilities are defined by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565881">KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS</a> property. Other scanning capabilities to support other broadcast standards (for example, DVB-S) are not yet supported. 


### -field lengthofBucket

The number of GUIDs in the <b>GUIDBucket</b> array. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565881">KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS</a>

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565887">KSPROPERTY_TUNER_SCAN_CAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TUNER_SCAN_CAPS_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

