---
UID: NS:ksmedia.__unnamed_struct_139
title: KSPROPERTY_CROSSBAR_PININFO_S (ksmedia.h)
description: The KSPROPERTY_CROSSBAR_PININFO_S structure describes the crossbar pin information for a device.
old-location: stream\ksproperty_crossbar_pininfo_s.htm
tech.root: stream
ms.assetid: 7ddef9cf-aa2f-4383-b37f-8c2f3e9c99d6
ms.date: 04/23/2018
ms.keywords: "*PKSPROPERTY_CROSSBAR_PININFO_S, KSPROPERTY_CROSSBAR_PININFO_S, KSPROPERTY_CROSSBAR_PININFO_S structure [Streaming Media Devices], PKSPROPERTY_CROSSBAR_PININFO_S, PKSPROPERTY_CROSSBAR_PININFO_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CROSSBAR_PININFO_S, ksmedia/PKSPROPERTY_CROSSBAR_PININFO_S, stream.ksproperty_crossbar_pininfo_s, vidcapstruct_a8532e73-5b8e-4ed1-a27e-e151642fff2a.xml"
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSPROPERTY_CROSSBAR_PININFO_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_CROSSBAR_PININFO_S, *PKSPROPERTY_CROSSBAR_PININFO_S
---

# KSPROPERTY_CROSSBAR_PININFO_S structure


## -description


The KSPROPERTY_CROSSBAR_PININFO_S structure describes the crossbar pin information for a device.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field Direction

Specifies the minidriver-provided direction of data flow for the pin specified in <b>Index</b>. This value can be either <b>KSPIN_DATAFLOW_IN</b> or KSPIN_DATAFLOW_OUT.


### -field Index

Specifies the zero-based index of the pin for which crossbar information is being queried. Input pins are queried separately from output pins.


### -field PinType

Specifies the minidriver-provided type of physical connector. This member must be set to one of the KS_PhysicalConnectorType enumerated values defined in <i>ksmedia.h</i>:

KS_PhysConn_Video_Tuner

KS_PhysConn_Video_Composite

KS_PhysConn_Video_Svideo

KS_PhysConn_Video_RGB

KS_PhysConn_Video_YRYBY

KS_PhysConn_Video_SerialDigital

KS_PhysConn_Video_ParallelDigital

KS_PhysConn_Video_SCSI

KS_PhysConn_Video_AUX

KS_PhysConn_Video_Video_1394

KS_PhysConn_Video_USB

KS_PhysConn_Video_VideoDecoder

KS_PhysConn_Video_VideoEncoder

KS_PhysConn_Video_SCART

KS_PhysConn_Audio_Tuner

KS_PhysConn_Audio_Line

KS_PhysConn_Audio_Misc

KS_PhysConn_Audio_AESDigital

KS_PhysConn_Audio_SPDIFDigital

KS_PhysConn_Audio_SCSI

KS_PhysConn_Audio_AUX

KS_PhysConn_Audio_1394

KS_PhysConn_Audio_USB

KS_PhysConn_Audio_AudioDecoder


### -field RelatedPinIndex

Specifies the optional pin index of a pin that is related to the pin specified in <b>Index</b>. For example, the minidriver can set the <b>RelatedPinIndex</b> to the pin index of the audio stream that goes with a video stream in <b>Index</b>. <b>RelatedPinIndex</b> applies only to pins of the same direction (input or output) as the pin being queried. If no other pins are related to the current pin, the minidriver should return (-1).


### -field Medium

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563538">KSPIN_MEDIUM</a> structure that represents the hardware connection for the pin. This information is returned by the minidriver.


## -remarks



All index values are zero-based, and input pins are counted separately from output pins.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565121">KSPROPERTY_CROSSBAR_PININFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567804">PROPSETID_VIDCAP_CROSSBAR</a>
 

 

