---
UID: NF:wudfddi.IWDFInterrupt.SetExtendedPolicy
title: IWDFInterrupt::SetExtendedPolicy method
author: windows-driver-content
description: The SetExtendedPolicy method specifies the interrupt priority, processor affinity, affinity policy, and processor group for a specified interrupt.
old-location: wdf\iwdfinterrupt_setextendedpolicy.htm
old-project: wdf
ms.assetid: 6637E939-010E-4462-92CE-50C4DB867694
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: SetExtendedPolicy method, umdf.iwdfinterrupt_setextendedpolicy, IWDFInterrupt, IWDFInterrupt::SetExtendedPolicy, SetExtendedPolicy method, IWDFInterrupt interface, SetExtendedPolicy, wudfddi/IWDFInterrupt::SetExtendedPolicy, IWDFInterrupt interface, SetExtendedPolicy method, wdf.iwdfinterrupt_setextendedpolicy
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFInterrupt.SetExtendedPolicy
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFInterrupt::SetExtendedPolicy method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetExtendedPolicy</b> method specifies the interrupt priority, processor affinity, affinity policy, and processor group for a specified interrupt.
  


## -syntax


````
void SetExtendedPolicy(
  [in] WDF_INTERRUPT_EXTENDED_POLICY *PolicyAndGroup
);
````


## -parameters




### -param PolicyAndGroup [in]

A pointer to a caller-allocated <a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_extended_policy.md">WDF_INTERRUPT_EXTENDED_POLICY</a> structure that the driver has previously initialized by calling <a href="..\wudfinterrupt\nf-wudfinterrupt-wdf_interrupt_extended_policy_init.md">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a>.


## -returns



This method does not return a value.




## -remarks



This method is equivalent to KMDF’s <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptsetextendedpolicy.md">WdfInterruptSetExtendedPolicy</a>. See the Remarks section of <b>WdfInterruptSetExtendedPolicy</b> for more information about this method.



If a driver is running on an operating system version that is earlier than Windows 7, the framework ignores the value that the driver specifies for the processor group number when it calls <b>SetExtendedPolicy</b>.

For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.


#### Examples

The following code example calls <a href="..\wudfinterrupt\nf-wudfinterrupt-wdf_interrupt_extended_policy_init.md">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a> to initialize a <a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_extended_policy.md">WDF_INTERRUPT_EXTENDED_POLICY</a> structure; sets values for the policy, priority, and target processor set; and calls <b>SetExtendedPolicy</b>. The example sets normal priority for the interrupt and assigns the interrupt to processor 0 in processor group 2. 

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

WDF_INTERRUPT_EXTENDED_POLICY_INIT(&amp;myExtendedPolicy);
myExtendedPolicy.Policy = WdfIrqPolicySpecifiedProcessors;
myExtendedPolicy.Priority = WdfIrqPriorityNormal;
myExtendedPolicy.TargetProcessorSetAndGroup.Mask = AFFINITY_MASK(0);
myExtendedPolicy.TargetProcessorSetAndGroup.Group = 2;

pInterrupt-&gt;SetExtendedPolicy(
                              &amp;myExtendedPolicy
 );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_extended_policy.md">WDF_INTERRUPT_EXTENDED_POLICY</a>



<a href="..\wudfddi\nn-wudfddi-iwdfinterrupt.md">IWDFInterrupt</a>



<a href="..\wudfinterrupt\nf-wudfinterrupt-wdf_interrupt_extended_policy_init.md">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFInterrupt::SetExtendedPolicy method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

