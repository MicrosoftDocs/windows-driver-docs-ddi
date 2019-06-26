---
UID: NS:ksmedia.tagKS_DATAFORMAT_VBIINFOHEADER
title: tagKS_DATAFORMAT_VBIINFOHEADER (ksmedia.h)
description: The KS_DATAFORMAT_VBIINFOHEADER structure describes a vertical blanking interval (VBI) stream.
old-location: stream\ks_dataformat_vbiinfoheader.htm
tech.root: stream
ms.assetid: 597b081f-d2ff-4e20-b352-2082f1ef4d45
ms.date: 04/23/2018
ms.keywords: "*PKS_DATAFORMAT_VBIINFOHEADER, KS_DATAFORMAT_VBIINFOHEADER, KS_DATAFORMAT_VBIINFOHEADER structure [Streaming Media Devices], PKS_DATAFORMAT_VBIINFOHEADER, PKS_DATAFORMAT_VBIINFOHEADER structure pointer [Streaming Media Devices], ksmedia/KS_DATAFORMAT_VBIINFOHEADER, ksmedia/PKS_DATAFORMAT_VBIINFOHEADER, stream.ks_dataformat_vbiinfoheader, tagKS_DATAFORMAT_VBIINFOHEADER, vidcapstruct_67cdb187-7d2b-464b-a871-6b2f18a9839f.xml"
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
- KS_DATAFORMAT_VBIINFOHEADER
product:
- Windows
targetos: Windows
req.typenames: KS_DATAFORMAT_VBIINFOHEADER, *PKS_DATAFORMAT_VBIINFOHEADER
---

# tagKS_DATAFORMAT_VBIINFOHEADER structure


## -description


The KS_DATAFORMAT_VBIINFOHEADER structure describes a vertical blanking interval (VBI) stream.


## -struct-fields




### -field DataFormat

Specifies the data format being proposed.


### -field VBIInfoHeader

Describes VBI-specific information about the proposed connection.


## -remarks



This structure is used when a connection to a VBI pin is being proposed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-tagks_vbiinfoheader">KS_VBIINFOHEADER</a>
 

 

