---
UID: NE:ksmedia.__unnamed_enum_112
title: KS_AMVP_SELECTFORMATBY (ksmedia.h)
description: The KS_AMVP_SELECTFORMATBY enumeration specifies the criteria that the Overlay Mixer Filter should use to select the video format.
old-location: stream\ks_amvp_selectformatby.htm
tech.root: stream
ms.assetid: b7fb6752-9711-4922-a806-915c362bcffe
ms.date: 04/23/2018
keywords: ["KS_AMVP_SELECTFORMATBY enumeration"]
ms.keywords: KS_AMVP_BEST_BANDWIDTH, KS_AMVP_DO_NOT_CARE, KS_AMVP_INPUT_SAME_AS_OUTPUT, KS_AMVP_SELECTFORMATBY, KS_AMVP_SELECTFORMATBY enumeration [Streaming Media Devices], ksmedia/KS_AMVP_BEST_BANDWIDTH, ksmedia/KS_AMVP_DO_NOT_CARE, ksmedia/KS_AMVP_INPUT_SAME_AS_OUTPUT, ksmedia/KS_AMVP_SELECTFORMATBY, stream.ks_amvp_selectformatby, vidcapstruct_98fc9313-4177-46c2-8740-f0dc2857b447.xml
f1_keywords:
 - "ksmedia/KS_AMVP_SELECTFORMATBY"
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
- KS_AMVP_SELECTFORMATBY
product:
- Windows
targetos: Windows
req.typenames: KS_AMVP_SELECTFORMATBY
---

# KS_AMVP_SELECTFORMATBY enumeration


## -description


The KS_AMVP_SELECTFORMATBY enumeration specifies the criteria that the Overlay Mixer Filter should use to select the video format.


## -enum-fields




### -field KS_AMVP_DO_NOT_CARE

The format does not matter.


### -field KS_AMVP_BEST_BANDWIDTH

Use the largest available bandwidth.


### -field KS_AMVP_INPUT_SAME_AS_OUTPUT

Use the same format for output as input.

