---
UID: NF:wdfinterrupt.WDF_INTERRUPT_EXTENDED_POLICY_INIT
title: WDF_INTERRUPT_EXTENDED_POLICY_INIT function
author: windows-driver-content
description: The WDF_INTERRUPT_EXTENDED_POLICY_INIT function initializes a WDF_INTERRUPT_EXTENDED_POLICY structure.
old-location: wdf\wdf_interrupt_extended_policy_init.htm
tech.root: wdf
ms.assetid: fcc1e631-c77b-483b-9b5e-ec8d643f9930
ms.date: 02/26/2018
ms.keywords: DFInterruptObjectRef_47d18efc-03a4-47b7-a022-ba9ed3247f1f.xml, WDF_INTERRUPT_EXTENDED_POLICY_INIT, WDF_INTERRUPT_EXTENDED_POLICY_INIT function, kmdf.wdf_interrupt_extended_policy_init, wdf.wdf_interrupt_extended_policy_init, wdfinterrupt/WDF_INTERRUPT_EXTENDED_POLICY_INIT
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfinterrupt.h
api_name:
-	WDF_INTERRUPT_EXTENDED_POLICY_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_INTERRUPT_EXTENDED_POLICY_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_INTERRUPT_EXTENDED_POLICY_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552349">WDF_INTERRUPT_EXTENDED_POLICY</a> structure.


## -parameters




### -param ExtendedPolicy

<p>A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/Ff552349(v=VS.85).aspx"><b>WDF_INTERRUPT_EXTENDED_POLICY</b></a> structure.</p>




## -returns



None.




## -remarks



The <b>WDF_INTERRUPT_EXTENDED_POLICY_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552349">WDF_INTERRUPT_EXTENDED_POLICY</a> structure and sets the structure's <b>Size</b> member. It also sets the structure's <b>Policy</b> member to <b>WdfIrqPolicyMachineDefault</b> and sets the structure's <b>Priority</b> member to <b>WdfIrqPriorityUndefined</b>.


#### Examples

For a code example that uses <b>WDF_INTERRUPT_EXTENDED_POLICY_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547381">WdfInterruptSetExtendedPolicy</a>. 

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552349">WDF_INTERRUPT_EXTENDED_POLICY</a>
 

 

