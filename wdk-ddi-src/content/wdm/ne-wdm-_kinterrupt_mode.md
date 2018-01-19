---
UID: NE:wdm._KINTERRUPT_MODE
title: _KINTERRUPT_MODE
author: windows-driver-content
description: The KINTERRUPT_MODE enumeration type indicates whether an interrupt is level-triggered or edge-triggered.
old-location: kernel\kinterrupt_mode.htm
old-project: kernel
ms.assetid: 2f00fe3f-d73d-4f0f-a1dd-ae72fa57e55d
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _KINTERRUPT_MODE, KINTERRUPT_MODE
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
req.alt-api: KINTERRUPT_MODE
req.alt-loc: wdm.h
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
req.typenames: KINTERRUPT_MODE
req.product: Windows 10 or later.
---

# _KINTERRUPT_MODE enumeration



## -description
The <b>KINTERRUPT_MODE</b> enumeration type indicates whether an interrupt is level-triggered or edge-triggered.



## -syntax

````
typedef enum _KINTERRUPT_MODE { 
  LevelSensitive  = 0,
  Latched         = 1
} KINTERRUPT_MODE;
````


## -enum-fields

### -field LevelSensitive

The interrupt is level-triggered. This is the mode for traditional PCI line-based interrupts.


### -field Latched

The interrupt is edge-triggered. This is the mode for PCI message-signaled interrupts. 


## -remarks
The interrupt mode is an electrical characteristic of the interrupt. A device signals a level-triggered interrupt by changing the voltage on the interrupt pin, and holding it there until the processor signals that the interrupt is received. In contrast, to signal an edge-triggered interrupt, the device changes the voltage state for a fixed period of time, before reverting to the original voltage state.


## -see-also
<dl>
<dt>
<a href="..\wdm\ne-wdm-_kinterrupt_polarity.md">KINTERRUPT_POLARITY</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KINTERRUPT_MODE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

