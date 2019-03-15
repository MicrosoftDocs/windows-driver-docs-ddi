---
UID: NS:avcstrm._AVCSTRM_FORMAT_INFO
title: _AVCSTRM_FORMAT_INFO (avcstrm.h)
description: The AVCSTRM_FORMAT_INFO structure is used to describe a data stream.
old-location: stream\avcstrm_format_info.htm
tech.root: stream
ms.assetid: de8e262b-bcb9-4549-94cc-0a73df45bddc
ms.date: 04/23/2018
ms.keywords: "*PAVCSTRM_FORMAT_INFO, AVCSTRM_FORMAT_INFO, AVCSTRM_FORMAT_INFO structure [Streaming Media Devices], PAVCSTRM_FORMAT_INFO, PAVCSTRM_FORMAT_INFO structure pointer [Streaming Media Devices], _AVCSTRM_FORMAT_INFO, avcsref_e41f0bb0-8407-4338-9a68-46c00116ae92.xml, avcstrm/AVCSTRM_FORMAT_INFO, avcstrm/PAVCSTRM_FORMAT_INFO, stream.avcstrm_format_info"
ms.topic: struct
req.header: avcstrm.h
req.include-header: Avcstrm.h
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
- avcstrm.h
api_name:
- AVCSTRM_FORMAT_INFO
product:
- Windows
targetos: Windows
req.typenames: AVCSTRM_FORMAT_INFO, *PAVCSTRM_FORMAT_INFO
---

# _AVCSTRM_FORMAT_INFO structure


## -description


The AVCSTRM_FORMAT_INFO structure is used to describe a data stream.


## -struct-fields




### -field SizeOfThisBlock

Specifies the size of this data structure, in bytes.


### -field AVCStrmFormat

Specifies one of the AV/C streaming subunit formats defined in <a href="https://msdn.microsoft.com/library/windows/hardware/ff554114">AVCSTRM_FORMAT</a>.


### -field cipHdr1

Specifies the definition of the first quadlet of the two quadlet CIP header.


### -field cipHdr2

Specifies the definition of the second quadlet of the two quadlet CIP header.


### -field SrcPacketsPerFrame

Specifies the number of source packets to fill a data frame.


### -field FrameSize

Specifies the data buffer size.


### -field NumOfRcvBuffers

Specifies the number of receiving buffers.


### -field NumOfXmtBuffers

Specifies the number of transmitting buffers.


### -field OptionFlags

Specifies any option flags. Currently, only one flag is defined:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>


<dl>
<dt><a id="AVCSTRM_FORMAT_OPTION_STRIP_SPH"></a><a id="avcstrm_format_option_strip_sph"></a>AVCSTRM_FORMAT_OPTION_STRIP_SPH</dt>
<dd></dd>
</dl>
</td>
<td>
Strip the SPH (source packet header) from the 192-byte data packet for MPEG2TS.

</td>
</tr>
</table>
 


### -field AvgTimePerFrame

Specifies the average time per frame in 100 nanosecond units.


### -field BlockPeriod

Specifies the block period. This is used for transmit only. It is calculated from 1/ BlockPerSecond * 1,000,000,000 picoseconds. For SDDV, it transmits one block per 1394 cycle. 1/(29.97 * 250) * 1,000,000,000,000 = 133,466,800 picoseconds.


### -field Reserved

Reserved. Do not use. Must be set to 0.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554114">AVCSTRM_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557668">CIP_HDR1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557669">CIP_HDR2_FDF</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557672">CIP_HDR2_MPEGTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557676">CIP_HDR2_SYT</a>
 

 

