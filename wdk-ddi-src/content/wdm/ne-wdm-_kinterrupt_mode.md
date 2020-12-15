---
UID: NE:wdm._KINTERRUPT_MODE
title: _KINTERRUPT_MODE (wdm.h)
description: The KINTERRUPT_MODE enumeration type indicates whether an interrupt is level-triggered or edge-triggered.
old-location: kernel\kinterrupt_mode.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KINTERRUPT_MODE enumeration"]
ms.keywords: KINTERRUPT_MODE, KINTERRUPT_MODE enumeration [Kernel-Mode Driver Architecture], Latched, LevelSensitive, _KINTERRUPT_MODE, kernel.kinterrupt_mode, sysenum_35275927-b863-496a-8193-579f9d1d3a22.xml, wdm/KINTERRUPT_MODE, wdm/Latched, wdm/LevelSensitive
req.header: wdm.h
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
targetos: Windows
req.typenames: KINTERRUPT_MODE
f1_keywords:
 - _KINTERRUPT_MODE
 - wdm/_KINTERRUPT_MODE
 - KINTERRUPT_MODE
 - wdm/KINTERRUPT_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - KINTERRUPT_MODE
---

# _KINTERRUPT_MODE enumeration (wdm.h)


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

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterrupt">IoConnectInterrupt</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterruptex">IoConnectInterruptEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_polarity">KINTERRUPT_POLARITY</a>
