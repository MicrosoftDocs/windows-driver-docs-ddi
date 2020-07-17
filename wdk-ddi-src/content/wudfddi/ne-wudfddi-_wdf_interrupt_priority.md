---
UID: NE:wudfddi._WDF_INTERRUPT_PRIORITY
title: _WDF_INTERRUPT_PRIORITY (wudfddi.h)
description: The WDF_INTERRUPT_PRIORITY enumeration type identifies relative priorities for device interrupts.
old-location: wdf\wdf_interrupt_priority.htm
tech.root: wdf
ms.assetid: e3305a9c-8107-4631-974b-fe85779ec8dc
ms.date: 02/26/2018
keywords: ["_WDF_INTERRUPT_PRIORITY enumeration"]
ms.keywords: "*PWDF_INTERRUPT_PRIORITY, DFInterruptObjectRef_924e187c-58f4-4616-a505-6d1c03779f02.xml, PWDF_INTERRUPT_PRIORITY, PWDF_INTERRUPT_PRIORITY enumeration pointer, WDF_INTERRUPT_PRIORITY, WDF_INTERRUPT_PRIORITY enumeration, WdfIrqPriorityHigh, WdfIrqPriorityLow, WdfIrqPriorityNormal, WdfIrqPriorityUndefined, _WDF_INTERRUPT_PRIORITY, kmdf.wdf_interrupt_priority, wdf.wdf_interrupt_priority, wdfinterrupt/PWDF_INTERRUPT_PRIORITY, wdfinterrupt/WDF_INTERRUPT_PRIORITY, wdfinterrupt/WdfIrqPriorityHigh, wdfinterrupt/WdfIrqPriorityLow, wdfinterrupt/WdfIrqPriorityNormal, wdfinterrupt/WdfIrqPriorityUndefined"
f1_keywords:
 - "wudfddi/WDF_INTERRUPT_PRIORITY"
 - "WDF_INTERRUPT_PRIORITY"
req.header: wudfddi.h
req.include-header: Wdf.h, Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- wdfinterrupt.h
api_name:
- WDF_INTERRUPT_PRIORITY
product:
- Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
---

# _WDF_INTERRUPT_PRIORITY enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_INTERRUPT_PRIORITY</b> enumeration type identifies relative priorities for device interrupts.


## -enum-fields




### -field WdfIrqPriorityUndefined

The relative priority of a device's interrupt is undefined.


### -field WdfIrqPriorityLow

The device's interrupt has a relatively low priority, typically because the interrupt does not have to be serviced immediately.


### -field WdfIrqPriorityNormal

The device's interrupt priority is neither relatively low nor relatively high.


### -field WdfIrqPriorityHigh

The device's interrupt has a relatively high priority, typically because the interrupt must be serviced immediately.


## -remarks



The <b>WDF_INTERRUPT_PRIORITY</b> enumeration type is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptsetpolicy">WdfInterruptSetPolicy</a> method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptsetpolicy">WdfInterruptSetPolicy</a>
 

 

