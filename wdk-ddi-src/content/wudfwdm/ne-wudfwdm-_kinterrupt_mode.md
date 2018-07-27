---
UID: NE:wudfwdm._KINTERRUPT_MODE
title: "_KINTERRUPT_MODE"
author: windows-driver-content
description: The KINTERRUPT_MODE enumeration type indicates whether an interrupt is level-triggered or edge-triggered.
old-location: kernel\kinterrupt_mode.htm
tech.root: kernel
ms.assetid: 2f00fe3f-d73d-4f0f-a1dd-ae72fa57e55d
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KINTERRUPT_MODE, KINTERRUPT_MODE enumeration [Kernel-Mode Driver Architecture], Latched, LevelSensitive, _KINTERRUPT_MODE, kernel.kinterrupt_mode, sysenum_35275927-b863-496a-8193-579f9d1d3a22.xml, wdm/KINTERRUPT_MODE, wdm/Latched, wdm/LevelSensitive
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h, Wudfwdm.h
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
-	wdm.h
api_name:
-	KINTERRUPT_MODE
product:
- Windows
targetos: Windows
req.typenames: KINTERRUPT_MODE
---

# _KINTERRUPT_MODE enumeration


## -description


The <b>KINTERRUPT_MODE</b> enumeration type indicates whether an interrupt is level-triggered or edge-triggered.


## -enum-fields




### -field LevelSensitive

The interrupt is level-triggered. This is the mode for traditional PCI line-based interrupts.


### -field Latched

The interrupt is edge-triggered. This is the mode for PCI message-signaled interrupts. 


## -remarks



The interrupt mode is an electrical characteristic of the interrupt. A device signals a level-triggered interrupt by changing the voltage on the interrupt pin, and holding it there until the processor signals that the interrupt is received. In contrast, to signal an edge-triggered interrupt, the device changes the voltage state for a fixed period of time, before reverting to the original voltage state.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548371">IoConnectInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548378">IoConnectInterruptEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554243">KINTERRUPT_POLARITY</a>
 

 



