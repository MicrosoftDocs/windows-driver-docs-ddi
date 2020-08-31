---
UID: NF:wudfddi.IWDFInterrupt.SetPolicy
title: IWDFInterrupt::SetPolicy (wudfddi.h)
description: The SetPolicy method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt.
old-location: wdf\iwdfinterrupt_setpolicy.htm
tech.root: wdf
ms.assetid: EDBCBB37-41A4-4234-BE8C-4C8739BC287B
ms.date: 02/26/2018
keywords: ["IWDFInterrupt::SetPolicy"]
ms.keywords: IWDFInterrupt interface,SetPolicy method, IWDFInterrupt.SetPolicy, IWDFInterrupt::SetPolicy, SetPolicy, SetPolicy method, SetPolicy method,IWDFInterrupt interface, umdf.iwdfinterrupt_setpolicy, wdf.iwdfinterrupt_setpolicy, wudfddi/IWDFInterrupt::SetPolicy
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFInterrupt::SetPolicy
 - wudfddi/IWDFInterrupt::SetPolicy
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFInterrupt.SetPolicy
---

# IWDFInterrupt::SetPolicy


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetPolicy</b> method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt.

## -parameters

### -param Policy 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/ne-wudfinterrupt-_wdf_interrupt_policy">WDF_INTERRUPT_POLICY</a>-typed enumerator that specifies a processor affinity policy for the interrupt.

### -param Priority 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ne-wdfinterrupt-_wdf_interrupt_priority">WDF_INTERRUPT_PRIORITY</a>-typed enumerator that specifies a priority for the interrupt.

### -param TargetProcessorSet 

[in]
A [**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity)-typed value that specifies a processor affinity for the interrupt, if the <i>Policy</i> parameter is set to <b>WdfIrqPolicySpecifiedProcessors</b>.

## -remarks

Starting in Windows Vista, drivers can specify an interrupt's priority, processor affinity, and affinity policy. For more information about how to use the registry to override the values that <b>SetPolicy</b> sets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority">Interrupt Affinity and Priority</a>.


If a driver is running on an operating system version that is earlier than Windows Vista, the framework ignores the values that the driver specifies when it calls <b>SetPolicy</b>.


For more information about registry values and INF sections that specify an interrupt's priority, processor affinity, and affinity policy, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority">Interrupt Affinity and Priority</a>.


If a driver calls <b>SetPolicy</b>, it must do so in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-idriverentry-ondeviceadd">IDriverEntry::OnDeviceAdd</a> callback function, after calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createinterrupt">IWDFDevice3::CreateInterrupt</a> method.

For more information about handling interrupts in UMDF drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-hardware-and-handling-interrupts">Accessing Hardware and Handling Interrupts</a>.


#### Examples

The following code example assigns a device interrupt to processor 0, with normal priority.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define AFFINITY_MASK(n) ((ULONG_PTR)1 << (n))

pIWdfInterrupt->SetPolicy(
                          WdfIrqPolicySpecifiedProcessors,
                          WdfIrqPriorityNormal,
                          AFFINITY_MASK(0)
                          );
</pre>
</td>
</tr>
</table></span></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfinterrupt">IWDFInterrupt</a>



[**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity)



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/ne-wudfinterrupt-_wdf_interrupt_policy">WDF_INTERRUPT_POLICY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ne-wdfinterrupt-_wdf_interrupt_priority">WDF_INTERRUPT_PRIORITY</a>

