---
UID: NS:hdaudio._HDAUDIO_CODEC_COMMAND
title: "_HDAUDIO_CODEC_COMMAND"
author: windows-driver-content
description: The HDAUDIO_CODEC_COMMAND structure specifies a codec command.
old-location: audio\hdaudio_codec_command.htm
old-project: audio
ms.assetid: 803e3506-fb63-4d64-b562-1956e99f9d9b
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PHDAUDIO_CODEC_COMMAND, HDAUDIO_CODEC_COMMAND, HDAUDIO_CODEC_COMMAND structure [Audio Devices], PHDAUDIO_CODEC_COMMAND, PHDAUDIO_CODEC_COMMAND structure pointer [Audio Devices], _HDAUDIO_CODEC_COMMAND, aud-prop2_9e7db610-d310-4285-8556-7a88567c22b6.xml, audio.hdaudio_codec_command, hdaudio/HDAUDIO_CODEC_COMMAND, hdaudio/PHDAUDIO_CODEC_COMMAND"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hdaudio.h
req.include-header: Hdaudio.h
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
req.irql: PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hdaudio.h
apiname:
-	HDAUDIO_CODEC_COMMAND
product: Windows
targetos: Windows
req.typenames: HDAUDIO_CODEC_COMMAND, *PHDAUDIO_CODEC_COMMAND
---

# _HDAUDIO_CODEC_COMMAND structure


## -description


The HDAUDIO_CODEC_COMMAND structure specifies a codec command.


## -syntax


````
typedef struct _HDAUDIO_CODEC_COMMAND {
  union {
    struct {
      ULONG Data  :8;
      ULONG VerbId  :12;
      ULONG Node  :8;
      ULONG CodecAddress  :4;
    } Verb8;
    struct {
      ULONG Data  :16;
      ULONG VerbId  :4;
      ULONG Node  :8;
      ULONG CodecAddress  :4;
    } Verb16;
    ULONG  Command;
  };
} HDAUDIO_CODEC_COMMAND, *PHDAUDIO_CODEC_COMMAND;
````


## -struct-fields




### -field Verb8

Specifies an 8-bit payload command format. The members in the following table are part of the Verb8 structure.
		   
		


### -field Verb8.Data

Specifies an 8-bit data payload value for the 8-bit payload command format.


### -field Verb8.VerbId

Specifies a 12-bit verb identifier for the 8-bit payload command format.


### -field Verb8.Node

Specifies an 8-bit node identifier for the 8-bit payload command format.


### -field Verb8.CodecAddress

Specifies a 4-bit codec address for the 8-bit payload command format.


### -field Verb16

Specifies an 16-bit payload command format. The members in the following table are part of the Verb16 structure.
		   
		


### -field Verb16.Data

Specifies an 16-bit data payload value for the 16-bit payload command format.


### -field Verb16.VerbId

Specifies a 4-bit verb identifier for the 16-bit payload command format.


### -field Verb16.Node

Specifies an 8-bit node identifier for the 16-bit payload command format.


### -field Verb16.CodecAddress

Specifies a 4-bit codec address for the 16-bit payload command format.


#### - Command

Specifies a 32-bit codec command that contains payload data, a verb identifier, a node identifier, and a codec address.


## -remarks



Clients call the <a href="..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md">TransferCodecVerbs</a> routine to pass commands to codecs. The commands are in the <a href="..\hdaudio\ns-hdaudio-_hdaudio_codec_transfer.md">HDAUDIO_CODEC_TRANSFER</a> structures that clients pass to this routine as call parameters. Before calling <b>TransferCodecVerbs</b>, function drivers can use the HDAUDIO_CODEC_COMMAND structure to encode the codec commands.

The validity of individual members depends on the type of command sent.




## -see-also

<a href="..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md">TransferCodecVerbs</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_codec_transfer.md">HDAUDIO_CODEC_TRANSFER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HDAUDIO_CODEC_COMMAND structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

