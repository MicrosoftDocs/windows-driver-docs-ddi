---
UID: NS:ksmedia.__unnamed_struct_109
title: KSEVENT_TUNER_INITIATE_SCAN_S (ksmedia.h)
description: The KSEVENT_TUNER_INITIATE_SCAN_S structure is used in the KSEVENT_TUNER_INITIATE_SCAN event within the EVENTSETID_TUNER event set.
old-location: stream\ksevent_tuner_initiate_scan_s.htm
tech.root: stream
ms.assetid: e690c596-d339-4489-97f3-02cacfdc5b04
ms.date: 04/30/2019
keywords: ["KSEVENT_TUNER_INITIATE_SCAN_S structure"]
ms.keywords: "*PKSEVENT_TUNER_INITIATE_SCAN_S, KSEVENT_TUNER_INITIATE_SCAN_S, KSEVENT_TUNER_INITIATE_SCAN_S structure [Streaming Media Devices], PKSEVENT_TUNER_INITIATE_SCAN_S, PKSEVENT_TUNER_INITIATE_SCAN_S structure pointer [Streaming Media Devices], ksmedia/KSEVENT_TUNER_INITIATE_SCAN_S, ksmedia/PKSEVENT_TUNER_INITIATE_SCAN_S, stream.ksevent_tuner_initiate_scan_s, vidcapstruct_569c5d77-3ec5-48ed-bf87-0c41297d8f9b.xml"
f1_keywords:
 - "ksmedia/KSEVENT_TUNER_INITIATE_SCAN_S"
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
- KSEVENT_TUNER_INITIATE_SCAN_S
product:
- Windows
targetos: Windows
req.typenames: KSEVENT_TUNER_INITIATE_SCAN_S, *PKSEVENT_TUNER_INITIATE_SCAN_S
---

# KSEVENT_TUNER_INITIATE_SCAN_S structure


## -description


The KSEVENT_TUNER_INITIATE_SCAN_S structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksevent-tuner-initiate-scan">KSEVENT_TUNER_INITIATE_SCAN</a> event within the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/eventsetid-tuner">EVENTSETID_TUNER</a> event set. 


## -struct-fields




### -field EventData

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a> that specifies the standard event structure, which contains the event handle that the driver notifies about the scan operation. 


### -field StartFrequency

The initial frequency, in Hz, for a scan operation. 


### -field EndFrequency

The final frequency, in Hz, for a scan operation.  


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/eventsetid-tuner">EVENTSETID_TUNER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksevent-tuner-initiate-scan">KSEVENT_TUNER_INITIATE_SCAN</a>
 

 

