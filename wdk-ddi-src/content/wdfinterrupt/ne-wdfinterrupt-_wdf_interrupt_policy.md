---
UID: NE:wdfinterrupt._WDF_INTERRUPT_POLICY
title: "_WDF_INTERRUPT_POLICY"
author: windows-driver-content
description: The WDF_INTERRUPT_POLICY enumeration type identifies the affinity policies that the PnP manager can use when it assigns a device's interrupts to the processors of a multiprocessor system.
old-location: wdf\wdf_interrupt_policy.htm
old-project: wdf
ms.assetid: 88f8f10d-bf1e-49bc-99c7-95a5e69c17e1
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: kmdf.wdf_interrupt_policy, wdfinterrupt/PWDF_INTERRUPT_POLICY, *PWDF_INTERRUPT_POLICY, wdfinterrupt/WdfIrqPolicyAllCloseProcessors, WDF_INTERRUPT_POLICY enumeration, WdfIrqPolicySpreadMessagesAcrossAllProcessors, PWDF_INTERRUPT_POLICY, WdfIrqPolicyAllProcessorsInMachine, WdfIrqPolicyMachineDefault, wdfinterrupt/WdfIrqPolicySpecifiedProcessors, wdfinterrupt/WDF_INTERRUPT_POLICY, wdf.wdf_interrupt_policy, WDF_INTERRUPT_POLICY, wdfinterrupt/WdfIrqPolicyMachineDefault, _WDF_INTERRUPT_POLICY, wdfinterrupt/WdfIrqPolicySpreadMessagesAcrossAllProcessors, wdfinterrupt/WdfIrqPolicyAllProcessorsInMachine, PWDF_INTERRUPT_POLICY enumeration pointer, WdfIrqPolicySpecifiedProcessors, WdfIrqPolicyOneCloseProcessor, DFInterruptObjectRef_e8b207c7-1a4a-4537-9aba-070ddcc426c1.xml, wdfinterrupt/WdfIrqPolicyOneCloseProcessor, WdfIrqPolicyAllCloseProcessors
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfinterrupt.h
apiname:
-	WDF_INTERRUPT_POLICY
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_POLICY, *PWDF_INTERRUPT_POLICY
req.product: Windows 10 or later.
---

# _WDF_INTERRUPT_POLICY enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_INTERRUPT_POLICY</b> enumeration type identifies the affinity policies that the PnP manager can use when it assigns a device's interrupts to the processors of a multiprocessor system.


## -syntax


````
typedef enum _WDF_INTERRUPT_POLICY { 
  WdfIrqPolicyMachineDefault                     = 0,
  WdfIrqPolicyAllCloseProcessors                 = 1,
  WdfIrqPolicyOneCloseProcessor                  = 2,
  WdfIrqPolicyAllProcessorsInMachine             = 3,
  WdfIrqPolicySpecifiedProcessors                = 4,
  WdfIrqPolicySpreadMessagesAcrossAllProcessors  = 5
} WDF_INTERRUPT_POLICY, *PWDF_INTERRUPT_POLICY;
````


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



The <b>WDF_INTERRUPT_POLICY</b> enumeration type is used as input to the <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptsetpolicy.md">WdfInterruptSetPolicy</a> method.




## -see-also

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptsetpolicy.md">WdfInterruptSetPolicy</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_INTERRUPT_POLICY enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

