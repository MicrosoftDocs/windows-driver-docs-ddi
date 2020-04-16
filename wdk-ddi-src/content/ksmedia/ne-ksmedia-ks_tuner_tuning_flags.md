---
UID: NE:ksmedia.__unnamed_enum_67
title: KS_TUNER_TUNING_FLAGS (ksmedia.h)
description: The KS_TUNER_TUNING_FLAGS enumeration defines tuning flags that describe the granularity of a tuning operation.
old-location: stream\ks_tuner_tuning_flags.htm
tech.root: stream
ms.assetid: f8742053-0d02-40af-9a6e-7af029db8575
ms.date: 04/23/2018
keywords: ["KS_TUNER_TUNING_FLAGS enumeration"]
ms.keywords: KS_TUNER_TUNING_COARSE, KS_TUNER_TUNING_EXACT, KS_TUNER_TUNING_FINE, KS_TUNER_TUNING_FLAGS, KS_TUNER_TUNING_FLAGS enumeration [Streaming Media Devices], ksmedia/KS_TUNER_TUNING_COARSE, ksmedia/KS_TUNER_TUNING_EXACT, ksmedia/KS_TUNER_TUNING_FINE, ksmedia/KS_TUNER_TUNING_FLAGS, stream.ks_tuner_tuning_flags, vidcapstruct_af322917-69e6-4688-885d-45422c594348.xml
f1_keywords:
 - "ksmedia/KS_TUNER_TUNING_FLAGS"
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
- KS_TUNER_TUNING_FLAGS
product:
- Windows
targetos: Windows
req.typenames: KS_TUNER_TUNING_FLAGS
---

# KS_TUNER_TUNING_FLAGS enumeration


## -description


The KS_TUNER_TUNING_FLAGS enumeration defines tuning flags that describe the granularity of a tuning operation.


## -enum-fields




### -field KS_TUNER_TUNING_EXACT

The tuner should tune directly to the specified frequency and bypass any fine tuning logic.


### -field KS_TUNER_TUNING_FINE

The tuning operation should perform a comprehensive search for the best tuning. This flag is used only if the strategy is KS_TUNER_STRATEGY_DRIVER_TUNES.


### -field KS_TUNER_TUNING_COARSE

The tuning operation should perform a fast search and attempt only to determine if a valid signal is present. This flag is used only if the strategy is KS_TUNER_STRATEGY_DRIVER_TUNES.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_tuner_frequency_s">KSPROPERTY_TUNER_FREQUENCY_S</a>
 

 

