---
UID: NS:hdaudio._HDAUDIO_CODEC_RESPONSE
title: _HDAUDIO_CODEC_RESPONSE (hdaudio.h)
description: The HDAUDIO_CODEC_RESPONSE structure specifies either a response to a codec command or an unsolicited response from a codec.
old-location: audio\hdaudio_codec_response.htm
tech.root: audio
ms.assetid: 56b9cdb5-2734-45b5-aeaf-ae6d606d1a5c
ms.date: 05/08/2018
keywords: ["_HDAUDIO_CODEC_RESPONSE structure"]
ms.keywords: "*PHDAUDIO_CODEC_RESPONSE, HDAUDIO_CODEC_RESPONSE, HDAUDIO_CODEC_RESPONSE structure [Audio Devices], PHDAUDIO_CODEC_RESPONSE, PHDAUDIO_CODEC_RESPONSE structure pointer [Audio Devices], _HDAUDIO_CODEC_RESPONSE, aud-prop2_2cf51d01-4493-439c-9a5f-30b86d76502b.xml, audio.hdaudio_codec_response, hdaudio/HDAUDIO_CODEC_RESPONSE, hdaudio/PHDAUDIO_CODEC_RESPONSE"
f1_keywords:
 - "hdaudio/HDAUDIO_CODEC_RESPONSE"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hdaudio.h
api_name:
- HDAUDIO_CODEC_RESPONSE
product:
- Windows
targetos: Windows
req.typenames: HDAUDIO_CODEC_RESPONSE, *PHDAUDIO_CODEC_RESPONSE
---

# _HDAUDIO_CODEC_RESPONSE structure


## -description


The HDAUDIO_CODEC_RESPONSE structure specifies either a response to a codec command or an unsolicited response from a codec.


## -struct-fields




### -field Unsolicited

 


### -field Unsolicited.Response

 


### -field Unsolicited.SubTag

 


### -field Unsolicited.Tag

 


### -field Response

 


### -field SDataIn

 


### -field IsUnsolicitedResponse

 


### -field HasFifoOverrun

 


### -field IsValid

 


### -field CompleteResponse

Specifies a complete, 64-bit response summary that consists of a 32-bit response, 4-bit codec address, three status bits, and 25 unused bits (set to zero). This value is mostly used in debug messages.


#### - ( unnamed struct )

Specifies a 26-bit unsolicited response value.



#### Unsolicited

Specifies a 32-bit unsolicited response value that consists of a 26-bit response value and a 6-bit tag value.



##### Response

Specifies a 26-bit unsolicited response value.



##### Tag

Specifies a 6-bit tag value for an unsolicited response.



#### Response

Specifies a 26-bit unsolicited response value.



#### SDataIn

Specifies the 4-bit codec address (SDI line) of the codec that generates the response.



#### IsUnsolicitedResponse

Specifies whether the response is unsolicited. If 1, the response is unsolicited. If 0, the response is solicited (that is, a response to a codec command).



#### HasFifoOverrun

Specifies whether a FIFO overrun occurred in the response input ring buffer (RIRB). If 1, a FIFO overrun occurred. If 0, a FIFO overrun did not occur.



#### IsValid

Specifies whether the response is valid. If 1, the response is valid. If 0, it is not valid.


## -remarks



After calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-ptransfer_codec_verbs">TransferCodecVerbs</a> routine, function drivers can use the HDAUDIO_CODEC_RESPONSE structure to decode the responses to their codec commands. The commands are contained in the HDAUDIO_CODEC_TRANSFER structures that clients pass to this routine as call parameters.

The callback for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_event_callback">RegisterEventCallback</a> routine also uses the HDAUDIO_CODEC_RESPONSE structure.

Most members of this structure contain hardware-generated values that the bus driver copies directly from the corresponding RIRB entry. The two exceptions are the values of the <b>IsValid</b> and <b>HasFifoOverrun</b> members, which the bus driver software writes to the structure to indicate the error status of the response. For information about the RIRB entry format, see the Intel High Definition Audio Specification at the <a href="https://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website.

If <b>IsValid</b>=0, one of the following has occurred:

<ul>
<li>
If <b>HasFifoOverrun</b>=1, the RIRB FIFO overflowed.

</li>
<li>
If <b>HasFifoOverrun</b>=0, the codec failed to respond.

</li>
</ul>
The unnamed 25-bitfield between the <b>UnsolicitedResponse</b> and <b>HasFifoOverrun</b> members is reserved for future expansion. The HD Audio bus controller currently writes zeros to this field.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_codec_transfer">HDAUDIO_CODEC_TRANSFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_event_callback">RegisterEventCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-ptransfer_codec_verbs">TransferCodecVerbs</a>
 

 

