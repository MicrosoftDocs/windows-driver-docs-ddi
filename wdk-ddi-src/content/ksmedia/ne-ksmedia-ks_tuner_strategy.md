---
UID: NE:ksmedia.KS_TUNER_STRATEGY
title: KS_TUNER_STRATEGY
author: windows-driver-content
description: The KS_TUNER_STRATEGY enumeration defines tuning method strategies.
old-location: stream\ks_tuner_strategy.htm
old-project: stream
ms.assetid: 333b1b11-cc6e-4546-9638-e5dcb4c2607c
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KS_TUNER_STRATEGY, KS_TUNER_STRATEGY enumeration [Streaming Media Devices], KS_TUNER_STRATEGY_DRIVER_TUNES, KS_TUNER_STRATEGY_PLL, KS_TUNER_STRATEGY_SIGNAL_STRENGTH, ksmedia/KS_TUNER_STRATEGY, ksmedia/KS_TUNER_STRATEGY_DRIVER_TUNES, ksmedia/KS_TUNER_STRATEGY_PLL, ksmedia/KS_TUNER_STRATEGY_SIGNAL_STRENGTH, stream.ks_tuner_strategy, vidcapstruct_99c03903-7b57-44ea-8c11-a3017931dfca.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KS_TUNER_STRATEGY
product:
- Windows
targetos: Windows
req.typenames: KS_TUNER_STRATEGY
---

# KS_TUNER_STRATEGY enumeration


## -description


The KS_TUNER_STRATEGY enumeration defines tuning method strategies.


## -enum-fields




### -field KS_TUNER_STRATEGY_PLL

The tuning accuracy for the device is measured by a phase locked loop (PLL) offset.


### -field KS_TUNER_STRATEGY_SIGNAL_STRENGTH

The tuning accuracy for the device is measured by signal strength.


### -field KS_TUNER_STRATEGY_DRIVER_TUNES

The minidriver has total control over the fine tuning process. No fine tuning is done by <i>Kstvtune.ax</i>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565872">KSPROPERTY_TUNER_MODE_CAPS_S</a>
 

 

