---
UID: NS:ksmedia.tagKS_AMVPDIMINFO
title: tagKS_AMVPDIMINFO (ksmedia.h)
description: The KS_AMVPDIMINFO structure is used to describe the dimensions of a video port.
old-location: stream\ks_amvpdiminfo.htm
tech.root: stream
ms.assetid: 5b8126ee-ba47-4eaf-887a-764e17a20e03
ms.date: 04/23/2018
keywords: ["tagKS_AMVPDIMINFO structure"]
ms.keywords: "*PKS_AMVPDIMINFO, KS_AMVPDIMINFO, KS_AMVPDIMINFO structure [Streaming Media Devices], PKS_AMVPDIMINFO, PKS_AMVPDIMINFO structure pointer [Streaming Media Devices], dvdref_4c6b6231-a3ef-49a5-8b27-c7ba0062c53a.xml, ksmedia/KS_AMVPDIMINFO, ksmedia/PKS_AMVPDIMINFO, stream.ks_amvpdiminfo, tagKS_AMVPDIMINFO"
f1_keywords:
 - "ksmedia/KS_AMVPDIMINFO"
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
- KS_AMVPDIMINFO
product:
- Windows
targetos: Windows
req.typenames: KS_AMVPDIMINFO, *PKS_AMVPDIMINFO
---

# tagKS_AMVPDIMINFO structure


## -description


The KS_AMVPDIMINFO structure is used to describe the dimensions of a video port.


## -struct-fields




### -field dwFieldWidth

Specifies the field width.


### -field dwFieldHeight

Specifies the field height.


### -field dwVBIWidth

Specifies the VBI data width.


### -field dwVBIHeight

Specifies the VBI data height.


### -field rcValidRegion

Describes a valid rectangle for data cropping.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_amvpdatainfo">KS_AMVPDATAINFO</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_amvpdatainfo">KS_AMVPDATAINFO</a>
 

 

