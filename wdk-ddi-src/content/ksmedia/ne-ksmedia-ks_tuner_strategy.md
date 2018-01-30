---
UID: NE:ksmedia.KS_TUNER_STRATEGY
title: KS_TUNER_STRATEGY
author: windows-driver-content
description: The KS_TUNER_STRATEGY enumeration defines tuning method strategies.
old-location: stream\ks_tuner_strategy.htm
old-project: stream
ms.assetid: 333b1b11-cc6e-4546-9638-e5dcb4c2607c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_TUNER_STRATEGY enumeration [Streaming Media Devices], ksmedia/KS_TUNER_STRATEGY_SIGNAL_STRENGTH, ksmedia/KS_TUNER_STRATEGY, KS_TUNER_STRATEGY_PLL, KS_TUNER_STRATEGY_SIGNAL_STRENGTH, ksmedia/KS_TUNER_STRATEGY_DRIVER_TUNES, vidcapstruct_99c03903-7b57-44ea-8c11-a3017931dfca.xml, KS_TUNER_STRATEGY, KS_TUNER_STRATEGY_DRIVER_TUNES, ksmedia/KS_TUNER_STRATEGY_PLL, stream.ks_tuner_strategy
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
-	KS_TUNER_STRATEGY
product: Windows
targetos: Windows
req.typenames: KS_TUNER_STRATEGY
---

# KS_TUNER_STRATEGY enumeration


## -description


The KS_TUNER_STRATEGY enumeration defines tuning method strategies.


## -syntax


````
typedef enum  { 
  KS_TUNER_STRATEGY_PLL              = 0X01,
  KS_TUNER_STRATEGY_SIGNAL_STRENGTH  = 0X02,
  KS_TUNER_STRATEGY_DRIVER_TUNES     = 0X04
} KS_TUNER_STRATEGY;
````


## -enum-fields




### -field KS_TUNER_STRATEGY_PLL

The tuning accuracy for the device is measured by a phase locked loop (PLL) offset.


### -field KS_TUNER_STRATEGY_SIGNAL_STRENGTH

The tuning accuracy for the device is measured by signal strength.


### -field KS_TUNER_STRATEGY_DRIVER_TUNES

The minidriver has total control over the fine tuning process. No fine tuning is done by <i>Kstvtune.ax</i>.


## -see-also

<a href="..\ksmedia\ns-ksmedia-ksproperty_tuner_mode_caps_s.md">KSPROPERTY_TUNER_MODE_CAPS_S</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_TUNER_STRATEGY enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

