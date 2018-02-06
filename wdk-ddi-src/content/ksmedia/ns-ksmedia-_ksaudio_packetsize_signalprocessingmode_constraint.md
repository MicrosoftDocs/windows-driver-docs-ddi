---
UID: NS:ksmedia._KSAUDIO_PACKETSIZE_SIGNALPROCESSINGMODE_CONSTRAINT
title: "_KSAUDIO_PACKETSIZE_SIGNALPROCESSINGMODE_CONSTRAINT"
author: windows-driver-content
description: The KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT structure describes the constraints specific to any signal processing mode.
old-location: audio\ksaudio_packetsize_processingmode_constraint.htm
old-project: audio
ms.assetid: 0BC6A03C-CF6D-4F56-985E-933E87200DFE
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "_KSAUDIO_PACKETSIZE_SIGNALPROCESSINGMODE_CONSTRAINT, KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT structure [Audio Devices], KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT, audio.ksaudio_packetsize_processingmode_constraint, ksmedia/KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
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
-	ksmedia.h
apiname:
-	KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT
product: Windows
targetos: Windows
req.typenames: KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT
---

# _KSAUDIO_PACKETSIZE_SIGNALPROCESSINGMODE_CONSTRAINT structure


## -description


The <b>KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT</b> structure describes the constraints specific to any signal processing mode.


## -syntax


````
typedef struct _KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT {
  GUID  ProcessingMode;
  ULONG SamplesPerProcessingPacket;
  ULONG ProcessingPacketDurationInHns;
} KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT;
````


## -struct-fields




### -field ProcessingMode

The signal processing mode that this constraint applies to.


### -field SamplesPerProcessingPacket

The processing frame size for the processing mode, expressed in number of samples. If this value is 0, the constraint is expressed by the <b>ProcessingPacketDurationInHns</b> field.


### -field ProcessingPacketDurationInHns

The processing frame size for the processing mode, expressed in hundred-nanosecond (HNS) units. This field is ignored if <b>SamplesPerProcessingPacket</b> is nonzero.


## -see-also

<a href="..\ksmedia\ns-ksmedia-_ksaudio_packetsize_constraints.md">KSAUDIO_PACKETSIZE_CONSTRAINTS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

