---
UID: NF:wudfddi.IWDFInterrupt.SetExtendedPolicy
title: IWDFInterrupt::SetExtendedPolicy (wudfddi.h)
description: The SetExtendedPolicy method specifies the interrupt priority, processor affinity, affinity policy, and processor group for a specified interrupt.
old-location: wdf\iwdfinterrupt_setextendedpolicy.htm
tech.root: wdf
ms.assetid: 6637E939-010E-4462-92CE-50C4DB867694
ms.date: 02/26/2018
ms.keywords: IWDFInterrupt interface,SetExtendedPolicy method, IWDFInterrupt.SetExtendedPolicy, IWDFInterrupt::SetExtendedPolicy, SetExtendedPolicy, SetExtendedPolicy method, SetExtendedPolicy method,IWDFInterrupt interface, umdf.iwdfinterrupt_setextendedpolicy, wdf.iwdfinterrupt_setextendedpolicy, wudfddi/IWDFInterrupt::SetExtendedPolicy
ms.topic: method
req.header: wudfddi.h
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
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFInterrupt.SetExtendedPolicy
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFInterrupt::SetExtendedPolicy


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetExtendedPolicy</b> method specifies the interrupt priority, processor affinity, affinity policy, and processor group for a specified interrupt.
  


## -parameters




### -param PolicyAndGroup [in]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552349">WDF_INTERRUPT_EXTENDED_POLICY</a> structure that the driver has previously initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552350">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a>.


## -returns



This method does not return a value.




## -remarks



This method is equivalent to KMDF’s <a href="https://msdn.microsoft.com/library/windows/hardware/ff547381">WdfInterruptSetExtendedPolicy</a>. See the Remarks section of <b>WdfInterruptSetExtendedPolicy</b> for more information about this method.



If a driver is running on an operating system version that is earlier than Windows 7, the framework ignores the value that the driver specifies for the processor group number when it calls <b>SetExtendedPolicy</b>.

For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.


#### Examples

The following code example calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff552350">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a> to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552349">WDF_INTERRUPT_EXTENDED_POLICY</a> structure; sets values for the policy, priority, and target processor set; and calls <b>SetExtendedPolicy</b>. The example sets normal priority for the interrupt and assigns the interrupt to processor 0 in processor group 2. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
IWDFInterrupt* pInterrupt;

#define AFFINITY_MASK(n) ((ULONG_PTR)1 &lt;&lt; (n))

WDF_INTERRUPT_EXTENDED_POLICY myExtendedPolicy;

WDF_INTERRUPT_EXTENDED_POLICY_INIT(&myExtendedPolicy);
myExtendedPolicy.Policy = WdfIrqPolicySpecifiedProcessors;
myExtendedPolicy.Priority = WdfIrqPriorityNormal;
myExtendedPolicy.TargetProcessorSetAndGroup.Mask = AFFINITY_MASK(0);
myExtendedPolicy.TargetProcessorSetAndGroup.Group = 2;

pInterrupt->SetExtendedPolicy(
                              &myExtendedPolicy
 );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451283">IWDFInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552349">WDF_INTERRUPT_EXTENDED_POLICY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552350">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a>
 

 

