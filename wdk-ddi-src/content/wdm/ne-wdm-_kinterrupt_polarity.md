---
UID: NE:wdm._KINTERRUPT_POLARITY
title: _KINTERRUPT_POLARITY
author: windows-driver-content
description: The KINTERRUPT_POLARITY enumeration indicates how a device signals an interrupt request on an interrupt line.
old-location: kernel\kinterrupt_polarity.htm
old-project: kernel
ms.assetid: 2fcc4597-b169-43a8-b2bb-dd2dd66f29dc
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: InterruptActiveBoth, wdm/InterruptActiveBothTriggerLow, *PKINTERRUPT_POLARITY, InterruptPolarityUnknown, wdm/InterruptRisingEdge, InterruptActiveLow, InterruptFallingEdge, PKINTERRUPT_POLARITY, InterruptActiveBothTriggerHigh, InterruptActiveHigh, wdm/InterruptActiveBothTriggerHigh, _KINTERRUPT_POLARITY, InterruptActiveBothTriggerLow, KINTERRUPT_POLARITY enumeration [Kernel-Mode Driver Architecture], wdm/InterruptPolarityUnknown, wdm/KINTERRUPT_POLARITY, wdm/PKINTERRUPT_POLARITY, wdm/InterruptActiveHigh, KINTERRUPT_POLARITY, wdm/InterruptActiveBoth, PKINTERRUPT_POLARITY enumeration pointer [Kernel-Mode Driver Architecture], wdm/InterruptFallingEdge, wdm/InterruptActiveLow, sysenum_56e5681d-ea77-4385-bd47-4add306a4fe8.xml, InterruptRisingEdge, kernel.kinterrupt_polarity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Wdm.h
apiname: 
-	KINTERRUPT_POLARITY
product: Windows
targetos: Windows
req.typenames: KINTERRUPT_POLARITY, *PKINTERRUPT_POLARITY
req.product: Windows 10 or later.
---

# _KINTERRUPT_POLARITY enumeration


## -description


The <b>KINTERRUPT_POLARITY</b> enumeration indicates how a device signals an interrupt request on an interrupt line.


## -syntax


````
typedef enum _KINTERRUPT_POLARITY { 
  InterruptPolarityUnknown,
  InterruptActiveHigh,
  InterruptRisingEdge             = InterruptActiveHigh,
  InterruptActiveLow,
  InterruptFallingEdge            = InterruptActiveLow,
  InterruptActiveBoth,
  InterruptActiveBothTriggerLow   = InterruptActiveBoth,
  InterruptActiveBothTriggerHigh
} KINTERRUPT_POLARITY, *PKINTERRUPT_POLARITY;
````


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


A <b>KINTERRUPT_POLARITY</b> enumeration constant is frequently used in conjunction with a <a href="..\wdm\ne-wdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a> enumeration constant to describe an interrupt signal. A <b>KINTERRUPT_MODE</b> enumeration constant indicates whether the interrupt signal from a device is level-triggered or edge-triggered.



## -see-also

<a href="..\wdm\ne-wdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KINTERRUPT_POLARITY enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

