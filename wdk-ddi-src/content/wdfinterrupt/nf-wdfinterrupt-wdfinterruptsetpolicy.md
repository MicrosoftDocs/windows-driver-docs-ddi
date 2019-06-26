---
UID: NF:wdfinterrupt.WdfInterruptSetPolicy
title: WdfInterruptSetPolicy function (wdfinterrupt.h)
description: The WdfInterruptSetPolicy method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt.
old-location: wdf\wdfinterruptsetpolicy.htm
tech.root: wdf
ms.assetid: f61bef13-d9b5-4e6a-8657-995a1fcbf7b1
ms.date: 02/26/2018
ms.keywords: DFInterruptObjectRef_86b7a562-3aee-4c0b-9a68-f98a2b76588f.xml, WdfInterruptSetPolicy, WdfInterruptSetPolicy method, kmdf.wdfinterruptsetpolicy, wdf.wdfinterruptsetpolicy, wdfinterrupt/WdfInterruptSetPolicy
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfInterruptSetPolicy
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfInterruptSetPolicy function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptSetPolicy</b> method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


### -param Policy [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/ne-wdfinterrupt-_wdf_interrupt_policy">WDF_INTERRUPT_POLICY</a>-typed enumerator that specifies a processor affinity policy for the interrupt.


### -param Priority [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/ne-wdfinterrupt-_wdf_interrupt_priority">WDF_INTERRUPT_PRIORITY</a>-typed enumerator that specifies a priority for the interrupt.


### -param TargetProcessorSet [in]

A [**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity)-typed value that specifies a processor affinity for the interrupt, if the <i>Policy</i> parameter is set to <b>WdfIrqPolicySpecifiedProcessors</b>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Windows Vista and later versions of the operating system allow drivers to specify an interrupt's priority, processor affinity, and affinity policy. For information about how to use the registry to override the values that <b>WdfInterruptSetPolicy</b> sets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority">Interrupt Affinity and Priority</a>.

If a driver is running on an operating system version that is earlier than Windows Vista, the framework ignores the values that the driver specifies when it calls <b>WdfInterruptSetPolicy</b>.

For more information about registry values and INF sections that specify an interrupt's priority, processor affinity, and affinity policy, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority">Interrupt Affinity and Priority</a>.

If a driver calls <b>WdfInterruptSetPolicy</b>, it typically does so in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function, after calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>.

If your driver creates interrupts in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>, do not use <b>WdfInterruptSetPolicy</b> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nf-wdfinterrupt-wdfinterruptsetextendedpolicy">WdfInterruptSetExtendedPolicy</a>. Instead, apply policy in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nc-wdffdo-evt_wdf_device_filter_resource_requirements">EvtDeviceFilterAddResourceRequirements</a>, by directly manipulating the interrupt resource requirement that this callback function receives in its <i>IoResourceRequirementsList</i> parameter.

For more information about handling interrupts in framework-based drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.


#### Examples

The following code example assigns a device interrupt to processor 0, with normal priority.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define AFFINITY_MASK(n) ((ULONG_PTR)1 << (n))

WdfInterruptSetPolicy(
                      Interrupt,
                      WdfIrqPolicySpecifiedProcessors,
                      WdfIrqPriorityNormal,
                      AFFINITY_MASK(0)
                      );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nf-wdfinterrupt-wdfinterruptsetextendedpolicy">WdfInterruptSetExtendedPolicy</a>
 

 

