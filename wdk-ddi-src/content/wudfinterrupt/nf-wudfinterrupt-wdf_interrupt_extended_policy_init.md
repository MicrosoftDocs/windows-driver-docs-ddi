---
UID: NF:wudfinterrupt.WDF_INTERRUPT_EXTENDED_POLICY_INIT
title: WDF_INTERRUPT_EXTENDED_POLICY_INIT function (wudfinterrupt.h)
description: The WDF_INTERRUPT_EXTENDED_POLICY_INIT function initializes a WDF_INTERRUPT_EXTENDED_POLICY structure.
old-location: wdf\wdf_interrupt_extended_policy_init_umdf.htm
tech.root: wdf
ms.assetid: 6CD02F5B-0E34-46F5-8AEA-3B30293E1875
ms.date: 02/26/2018
ms.keywords: WDF_INTERRUPT_EXTENDED_POLICY_INIT, WDF_INTERRUPT_EXTENDED_POLICY_INIT function, umdf.wdf_interrupt_extended_policy_init, wdf.wdf_interrupt_extended_policy_init_umdf, wudfinterrupt/WDF_INTERRUPT_EXTENDED_POLICY_INIT
ms.topic: function
req.header: wudfinterrupt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
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
-	Wudfinterrupt.h
api_name:
-	WDF_INTERRUPT_EXTENDED_POLICY_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_INTERRUPT_EXTENDED_POLICY_INIT function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff552350">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552349">WDF_INTERRUPT_EXTENDED_POLICY</a> structure.


## -parameters




### -param ExtendedPolicy

<p>A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/Ff552349(v=VS.85).aspx"><b>WDF_INTERRUPT_EXTENDED_POLICY</b></a> structure.</p>




## -returns



None




## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff552350">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552349">WDF_INTERRUPT_EXTENDED_POLICY</a> structure and sets the structure's <b>Size</b> member. It also sets the structure's <b>Policy</b> member to <b>WdfIrqPolicyMachineDefault</b> and sets the structure's <b>Priority</b> member to <b>WdfIrqPriorityUndefined</b>.


#### Examples

For a code example that uses <a href="https://msdn.microsoft.com/library/windows/hardware/ff552350">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a>, see <a href="https://msdn.microsoft.com/6637E939-010E-4462-92CE-50C4DB867694">IWDFInterrupt::SetExtendedPolicy</a>. 

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552349">WDF_INTERRUPT_EXTENDED_POLICY</a>
 

 

