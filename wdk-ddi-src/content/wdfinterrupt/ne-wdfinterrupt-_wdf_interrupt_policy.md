---
UID: NE:wdfinterrupt._WDF_INTERRUPT_POLICY
title: "_WDF_INTERRUPT_POLICY"
author: windows-driver-content
description: The WDF_INTERRUPT_POLICY enumeration type identifies the affinity policies that the PnP manager can use when it assigns a device's interrupts to the processors of a multiprocessor system.
old-location: wdf\wdf_interrupt_policy.htm
tech.root: wdf
ms.assetid: 88f8f10d-bf1e-49bc-99c7-95a5e69c17e1
ms.date: 02/26/2018
ms.keywords: "*PWDF_INTERRUPT_POLICY, DFInterruptObjectRef_e8b207c7-1a4a-4537-9aba-070ddcc426c1.xml, PWDF_INTERRUPT_POLICY, PWDF_INTERRUPT_POLICY enumeration pointer, WDF_INTERRUPT_POLICY, WDF_INTERRUPT_POLICY enumeration, WdfIrqPolicyAllCloseProcessors, WdfIrqPolicyAllProcessorsInMachine, WdfIrqPolicyMachineDefault, WdfIrqPolicyOneCloseProcessor, WdfIrqPolicySpecifiedProcessors, WdfIrqPolicySpreadMessagesAcrossAllProcessors, _WDF_INTERRUPT_POLICY, kmdf.wdf_interrupt_policy, wdf.wdf_interrupt_policy, wdfinterrupt/PWDF_INTERRUPT_POLICY, wdfinterrupt/WDF_INTERRUPT_POLICY, wdfinterrupt/WdfIrqPolicyAllCloseProcessors, wdfinterrupt/WdfIrqPolicyAllProcessorsInMachine, wdfinterrupt/WdfIrqPolicyMachineDefault, wdfinterrupt/WdfIrqPolicyOneCloseProcessor, wdfinterrupt/WdfIrqPolicySpecifiedProcessors, wdfinterrupt/WdfIrqPolicySpreadMessagesAcrossAllProcessors"
ms.topic: enum
req.header: wdfinterrupt.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfinterrupt.h
api_name:
-	WDF_INTERRUPT_POLICY
product:
- Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_POLICY, *PWDF_INTERRUPT_POLICY
---

# _WDF_INTERRUPT_POLICY enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_INTERRUPT_POLICY</b> enumeration type identifies the affinity policies that the PnP manager can use when it assigns a device's interrupts to the processors of a multiprocessor system.


## -enum-fields




### -field WdfIrqPolicyMachineDefault

Use the system's default affinity policy.


### -field WdfIrqPolicyAllCloseProcessors

For NUMA systems, the PnP manager should assign the device's interrupts to processors that are close to the device. For non-NUMA systems, specifying <b>WdfIrqPolicyAllCloseProcessors</b> is the same as specifying <b>WdfIrqPolicyAllProcessorsInMachine</b>.


### -field WdfIrqPolicyOneCloseProcessor

For NUMA systems, the PnP manager should assign one interrupt to a processor that is close to the device. For non-NUMA systems, the PnP manager can assign the interrupt to any processor.


### -field WdfIrqPolicyAllProcessorsInMachine

The PnP manager can assign a device's interrupts to any of the system's processors.


### -field WdfIrqPolicySpecifiedProcessors

The PnP manager should assign the device's interrupts only to specified processors.


### -field WdfIrqPolicySpreadMessagesAcrossAllProcessors

The PnP manager should assign different message-based interrupts to different processors, if possible. 


## -remarks



The <b>WDF_INTERRUPT_POLICY</b> enumeration type is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547387">WdfInterruptSetPolicy</a> method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547387">WdfInterruptSetPolicy</a>
 

 

