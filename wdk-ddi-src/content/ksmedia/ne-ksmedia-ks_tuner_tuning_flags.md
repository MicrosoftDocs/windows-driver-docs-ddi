---
UID: NE:ksmedia.KS_TUNER_TUNING_FLAGS
title: KS_TUNER_TUNING_FLAGS
author: windows-driver-content
description: The KS_TUNER_TUNING_FLAGS enumeration defines tuning flags that describe the granularity of a tuning operation.
old-location: stream\ks_tuner_tuning_flags.htm
old-project: stream
ms.assetid: f8742053-0d02-40af-9a6e-7af029db8575
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_TUNER_TUNING_COARSE, stream.ks_tuner_tuning_flags, vidcapstruct_af322917-69e6-4688-885d-45422c594348.xml, ksmedia/KS_TUNER_TUNING_FLAGS, ksmedia/KS_TUNER_TUNING_FINE, KS_TUNER_TUNING_EXACT, ksmedia/KS_TUNER_TUNING_COARSE, KS_TUNER_TUNING_FLAGS enumeration [Streaming Media Devices], KS_TUNER_TUNING_FLAGS, ksmedia/KS_TUNER_TUNING_EXACT, KS_TUNER_TUNING_FINE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KS_TUNER_TUNING_FLAGS
product: Windows
targetos: Windows
req.typenames: KS_TUNER_TUNING_FLAGS
---

# KS_TUNER_TUNING_FLAGS enumeration


## -description


The KS_TUNER_TUNING_FLAGS enumeration defines tuning flags that describe the granularity of a tuning operation.


## -syntax


````
typedef enum  { 
  KS_TUNER_TUNING_EXACT   = 1,
  KS_TUNER_TUNING_FINE    = 2,
  KS_TUNER_TUNING_COARSE  = 3
} KS_TUNER_TUNING_FLAGS;
````


## -enum-fields




### -field KS_TUNER_TUNING_EXACT

The tuner should tune directly to the specified frequency and bypass any fine tuning logic.


### -field KS_TUNER_TUNING_FINE

The tuning operation should perform a comprehensive search for the best tuning. This flag is used only if the strategy is KS_TUNER_STRATEGY_DRIVER_TUNES.


### -field KS_TUNER_TUNING_COARSE

The tuning operation should perform a fast search and attempt only to determine if a valid signal is present. This flag is used only if the strategy is KS_TUNER_STRATEGY_DRIVER_TUNES.


## -see-also

<a href="..\ksmedia\ns-ksmedia-ksproperty_tuner_frequency_s.md">KSPROPERTY_TUNER_FREQUENCY_S</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_TUNER_TUNING_FLAGS enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

