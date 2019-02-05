---
UID: NS:61883._CIP_TALK
title: _CIP_TALK (61883.h)
description: This structure is used to begin transmission.
old-location: ieee\cip_talk.htm
tech.root: IEEE
ms.assetid: DD5EB79D-122B-4D17-9109-37473AC49C4A
ms.date: 02/15/2018
ms.keywords: "*PCIP_TALK, 61883/CIP_TALK, 61883/PCIP_TALK, CIP_TALK, CIP_TALK structure [Buses], IEEE.cip_talk, PCIP_TALK, PCIP_TALK structure pointer [Buses], _CIP_TALK"
ms.topic: struct
req.header: 61883.h
req.include-header: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	CIP_TALK
product:
- Windows
targetos: Windows
req.typenames: CIP_TALK, *PCIP_TALK
---

# _CIP_TALK structure


## -description


This structure is used to begin transmission. The  request begins isochronous transmission on the specified connection. This request will start transmitting CIP packets, whether there are any frames attached. If no frames are attached, empty CIP packets are transmitted for every isochronous cycle.


## -struct-fields




### -field hConnect

On input, the handle of the connection to begin isochronous transmission.


## -remarks



In the request, Flags can have these values:




<dl>
<dt><a id="CIP_TALK_USE_SPH_TIMESTAMP"></a><a id="cip_talk_use_sph_timestamp"></a>CIP_TALK_USE_SPH_TIMESTAMP</dt>
<dd>
Indicates that the timestamp within the SPH should be used to calculate the timing of transmission of isochronous packets.

</dd>
<dt><a id="CIP_TALK_DOUBLE_BUFFER"></a><a id="cip_talk_double_buffer"></a>CIP_TALK_DOUBLE_BUFFER</dt>
<dd>
Indicates that when transmitting the attached frames should be double-buffered.

</dd>
</dl>


If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

If the protocol driver is unable to allocate resources, it sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INSUFFICIENT_RESOURCES.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
 

 

