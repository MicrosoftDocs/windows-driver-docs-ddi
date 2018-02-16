---
UID: NS:hdaudio._HDAUDIO_CONVERTER_FORMAT
title: "_HDAUDIO_CONVERTER_FORMAT"
author: windows-driver-content
description: The HDAUDIO_CONVERTER_FORMAT structure specifies the 16-bit encoded stream format for an input or output converter, as defined in the Intel High Definition Audio Specification (see the Intel HD Audio website).
old-location: audio\hdaudio_converter_format.htm
old-project: audio
ms.assetid: 623f58f6-db82-4a4a-bac3-cc821babfe99
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: "_HDAUDIO_CONVERTER_FORMAT, audio.hdaudio_converter_format, HDAUDIO_CONVERTER_FORMAT, hdaudio/PHDAUDIO_CONVERTER_FORMAT, *PHDAUDIO_CONVERTER_FORMAT, PHDAUDIO_CONVERTER_FORMAT, HDAUDIO_CONVERTER_FORMAT structure [Audio Devices], PHDAUDIO_CONVERTER_FORMAT structure pointer [Audio Devices], hdaudio/HDAUDIO_CONVERTER_FORMAT, aud-prop2_fbc3cdcb-94a1-43ef-bf23-4b1cca37e99d.xml"
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
-	HDAUDIO_CONVERTER_FORMAT
product: Windows
targetos: Windows
req.typenames: HDAUDIO_CONVERTER_FORMAT, *PHDAUDIO_CONVERTER_FORMAT
---

# _HDAUDIO_CONVERTER_FORMAT structure


## -description


The HDAUDIO_CONVERTER_FORMAT structure specifies the 16-bit encoded stream format for an input or output converter, as defined in the Intel High Definition Audio Specification (see the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website).


## -syntax


````
typedef struct _HDAUDIO_CONVERTER_FORMAT {
  union {
    struct {
      USHORT NumberOfChannels  :4;
      USHORT BitsPerSample  :3;
      USHORT   :1;
      USHORT SampleRate  :7;
      USHORT StreamType  :1;
    };
    USHORT ConverterFormat;
  };
} HDAUDIO_CONVERTER_FORMAT, *PHDAUDIO_CONVERTER_FORMAT;
````


## -struct-fields




### -field NumberOfChannels

 


### -field BitsPerSample

 


### -field SampleRate

 


### -field StreamType

 


### -field ConverterFormat

Specifies the stream's data format as an encoded 16-bit value. For more information, see the following Remarks section.


#### - ( unnamed struct )

Specifies the number of channels in the stream's data format. For more information, see the following Remarks section.



#### NumberOfChannels

Specifies the number of channels in the stream's data format. For more information, see the following Remarks section.



#### BitsPerSample

Specifies the number of bits per sample. For more information, see the following Remarks section.



#### SampleRate

Specifies the stream's sample rate. For more information, see the following Remarks section.



#### StreamType

Specifies the stream type. If <b>StreamType</b>=0, the stream contains PCM data. If <b>StreamType</b>=1, the stream contains non-PCM data.


## -remarks



For information about the encoding of the individual bitfields in the structure definition, see the discussion of the stream descriptor in the Intel High Definition Audio Specification at the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website.

The HD Audio bus driver sets the unnamed bitfield in the structure definition to zero.

The <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>, <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>, and <a href="..\hdaudio\nc-hdaudio-pchange_bandwidth_allocation.md">ChangeBandwidthAllocation</a> routines take as an input parameter an <a href="..\hdaudio\ns-hdaudio-_hdaudio_stream_format.md">HDAUDIO_STREAM_FORMAT</a> structure and output the corresponding HDAUDIO_CONVERTER_FORMAT structure. The caller can use the output value to program the input or output converters.

Each valid HDAUDIO_CONVERTER_FORMAT encoding has a one-to-one correspondence to an HDAUDIO_STREAM_FORMAT structure that contains a valid set of parameters.




## -see-also

<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pchange_bandwidth_allocation.md">ChangeBandwidthAllocation</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_stream_format.md">HDAUDIO_STREAM_FORMAT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HDAUDIO_CONVERTER_FORMAT structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

