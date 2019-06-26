---
UID: NS:bdamedia.tagKS_DATARANGE_BDA_TRANSPORT
title: tagKS_DATARANGE_BDA_TRANSPORT (bdamedia.h)
description: The KS_DATARANGE_BDA_TRANSPORT structure describes a range of data formats for a BDA transport stream.
old-location: stream\ks_datarange_bda_transport.htm
tech.root: stream
ms.assetid: cd7dbcfa-f339-421a-9cc6-f4c494f13a41
ms.date: 04/23/2018
ms.keywords: "*PKS_DATARANGE_BDA_TRANSPORT, KS_DATARANGE_BDA_TRANSPORT, KS_DATARANGE_BDA_TRANSPORT structure [Streaming Media Devices], PKS_DATARANGE_BDA_TRANSPORT, PKS_DATARANGE_BDA_TRANSPORT structure pointer [Streaming Media Devices], bdamedia/KS_DATARANGE_BDA_TRANSPORT, bdamedia/PKS_DATARANGE_BDA_TRANSPORT, bdaref_89717b68-2829-4f7a-bcdb-10e0b790308c.xml, stream.ks_datarange_bda_transport, tagKS_DATARANGE_BDA_TRANSPORT"
ms.topic: struct
req.header: bdamedia.h
req.include-header: Bdamedia.h
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
- bdamedia.h
api_name:
- KS_DATARANGE_BDA_TRANSPORT
product:
- Windows
targetos: Windows
req.typenames: KS_DATARANGE_BDA_TRANSPORT, *PKS_DATARANGE_BDA_TRANSPORT
---

# tagKS_DATARANGE_BDA_TRANSPORT structure


## -description


The KS_DATARANGE_BDA_TRANSPORT structure describes a range of data formats for a BDA transport stream. 


## -struct-fields




### -field DataRange

KSDATARANGE structure that describes a range of data formats.


### -field BdaTransportInfo

BDA_TRANSPORT_INFO structure that describes formatting for a BDA transport stream connection. 


## -remarks



A BDA_TRANSPORT_INFO structure in conjunction with a KSDATARANGE structure makes up a KS_DATARANGE_BDA_TRANSPORT data range. A data range describes a range of data formats. 

Pins of filters specify the data ranges they support to enable stream connections to pins of other filters that also support those data ranges.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/bda-stream-format-guids">BDA Stream Format GUIDs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bdamedia/ns-bdamedia-tagbda_transport_info">BDA_TRANSPORT_INFO</a>



<a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kspin_descriptor">KSPIN_DESCRIPTOR</a>
 

 

