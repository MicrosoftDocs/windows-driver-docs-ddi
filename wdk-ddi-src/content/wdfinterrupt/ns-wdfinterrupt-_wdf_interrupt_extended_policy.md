---
UID: NS:wdfinterrupt._WDF_INTERRUPT_EXTENDED_POLICY
title: "_WDF_INTERRUPT_EXTENDED_POLICY"
author: windows-driver-content
description: The WDF_INTERRUPT_EXTENDED_POLICY structure contains information about an interrupt's policy, priority, affinity, and group.
old-location: wdf\wdf_interrupt_extended_policy.htm
old-project: wdf
ms.assetid: 28cc79e8-7078-4b29-ab2a-2eeca5c5b8b3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_INTERRUPT_EXTENDED_POLICY, DFInterruptObjectRef_db1feccc-0171-4163-b95f-6be057430176.xml, PWDF_INTERRUPT_EXTENDED_POLICY, PWDF_INTERRUPT_EXTENDED_POLICY structure pointer, WDF_INTERRUPT_EXTENDED_POLICY, WDF_INTERRUPT_EXTENDED_POLICY structure, _WDF_INTERRUPT_EXTENDED_POLICY, kmdf.wdf_interrupt_extended_policy, wdf.wdf_interrupt_extended_policy, wdfinterrupt/PWDF_INTERRUPT_EXTENDED_POLICY, wdfinterrupt/WDF_INTERRUPT_EXTENDED_POLICY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
-	wdfinterrupt.h
api_name:
-	WDF_INTERRUPT_EXTENDED_POLICY
product:
- Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_EXTENDED_POLICY, *PWDF_INTERRUPT_EXTENDED_POLICY
---

# _WDF_INTERRUPT_EXTENDED_POLICY structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_INTERRUPT_EXTENDED_POLICY</b> structure contains information about an interrupt's policy, priority, affinity, and group.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Policy

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh464032">WDF_INTERRUPT_POLICY</a>-typed enumerator that specifies a processor affinity policy for the interrupt.


### -field Priority

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552355">WDF_INTERRUPT_PRIORITY</a>-typed enumerator that specifies a priority for the interrupt.


### -field TargetProcessorSetAndGroup

A GROUP_AFFINITY structure that specifies a processor group and a processor affinity mask within the group, if the <i>Policy</i> parameter is set to <b>WdfIrqPolicySpecifiedProcessors</b>. The GROUP_AFFINITY structure is defined in <i>Winnt.h</i>. 


## -remarks



The <b>WDF_INTERRUPT_EXTENDED_POLICY</b> structure is used as input the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547381">WdfInterruptSetExtendedPolicy</a>. 

To initialize a <b>WDF_INTERRUPT_EXTENDED_POLICY</b> structure, your driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff552350">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552350">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547381">WdfInterruptSetExtendedPolicy</a>
 

 

