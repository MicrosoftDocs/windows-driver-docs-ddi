---
UID: NE:miniport._KINTERRUPT_POLARITY
title: "_KINTERRUPT_POLARITY"
author: windows-driver-content
description: The KINTERRUPT_POLARITY enumeration indicates how a device signals an interrupt request on an interrupt line.
old-location: kernel\kinterrupt_polarity.htm
old-project: kernel
ms.assetid: 2fcc4597-b169-43a8-b2bb-dd2dd66f29dc
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PKINTERRUPT_POLARITY, InterruptActiveBoth, InterruptActiveBothTriggerHigh, InterruptActiveBothTriggerLow, InterruptActiveHigh, InterruptActiveLow, InterruptFallingEdge, InterruptPolarityUnknown, InterruptRisingEdge, KINTERRUPT_POLARITY, KINTERRUPT_POLARITY enumeration [Kernel-Mode Driver Architecture], PKINTERRUPT_POLARITY, PKINTERRUPT_POLARITY enumeration pointer [Kernel-Mode Driver Architecture], _KINTERRUPT_POLARITY, kernel.kinterrupt_polarity, sysenum_56e5681d-ea77-4385-bd47-4add306a4fe8.xml, wdm/InterruptActiveBoth, wdm/InterruptActiveBothTriggerHigh, wdm/InterruptActiveBothTriggerLow, wdm/InterruptActiveHigh, wdm/InterruptActiveLow, wdm/InterruptFallingEdge, wdm/InterruptPolarityUnknown, wdm/InterruptRisingEdge, wdm/KINTERRUPT_POLARITY, wdm/PKINTERRUPT_POLARITY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
-	Wdm.h
api_name:
-	KINTERRUPT_POLARITY
product: Windows
targetos: Windows
req.typenames: KINTERRUPT_POLARITY, *PKINTERRUPT_POLARITY
---

# _KINTERRUPT_POLARITY enumeration


## -description


The <b>KINTERRUPT_POLARITY</b> enumeration indicates how a device signals an interrupt request on an interrupt line.


## -enum-fields




### -field InterruptPolarityUnknown

The interrupt polarity is unknown.


### -field InterruptActiveHigh

Active-high interrupt. The interrupt input type is level-triggered, and an interrupt request is indicated by a high signal level on the interrupt line. The request remains active as long as the line remains high.


### -field InterruptRisingEdge

Rising-edge-triggered interrupt. The interrupt input type is edge-triggered, and an interrupt request is indicated by a low-to-high transition on the interrupt line.


### -field InterruptActiveLow

Active-low interrupt. The interrupt input type is level-triggered, and an interrupt request is indicated by a low signal level on the interrupt line. The request remains active as long as the line remains low.


### -field InterruptFallingEdge

Falling-edge-triggered interrupt. The interrupt input type is edge-triggered, and an interrupt request is indicated by a high-to-low transition on the interrupt line.


### -field InterruptActiveBoth

Active-both interrupt. The interrupt input type is edge-triggered, and an interrupt request is indicated by a low-to-high or a high-to-low transition on the interrupt line. After a low-to-high transition signals an interrupt request, the interrupt line remains high until a high-to-low transition signals the next interrupt request. Similarly, after a high-to-low transition signals an interrupt request, the interrupt line remains low until a low-to-high transition signals the next interrupt request.


### -field InterruptActiveBothTriggerLow

Reserved for use by the operating system.


### -field InterruptActiveBothTriggerHigh

Reserved for use by the operating system.


## -remarks



A <b>KINTERRUPT_POLARITY</b> enumeration constant is frequently used in conjunction with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554239">KINTERRUPT_MODE</a> enumeration constant to describe an interrupt signal. A <b>KINTERRUPT_MODE</b> enumeration constant indicates whether the interrupt signal from a device is level-triggered or edge-triggered.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554239">KINTERRUPT_MODE</a>
 

 

