---
UID: NF:wudfddi.IWDFInterrupt.SetPolicy
title: IWDFInterrupt::SetPolicy method
author: windows-driver-content
description: The SetPolicy method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt.
old-location: wdf\iwdfinterrupt_setpolicy.htm
old-project: wdf
ms.assetid: EDBCBB37-41A4-4234-BE8C-4C8739BC287B
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wudfddi/IWDFInterrupt::SetPolicy, SetPolicy method, IWDFInterrupt interface, SetPolicy method, IWDFInterrupt::SetPolicy, IWDFInterrupt interface, SetPolicy method, umdf.iwdfinterrupt_setpolicy, SetPolicy, IWDFInterrupt, wdf.iwdfinterrupt_setpolicy
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
-	IWDFInterrupt.SetPolicy
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFInterrupt::SetPolicy method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetPolicy</b> method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt.


## -syntax


````
void SetPolicy(
  [in] WDF_INTERRUPT_POLICY   Policy,
  [in] WDF_INTERRUPT_PRIORITY Priority,
  [in] KAFFINITY              TargetProcessorSet
);
````


## -parameters




### -param Policy [in]

A <a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_policy.md">WDF_INTERRUPT_POLICY</a>-typed enumerator that specifies a processor affinity policy for the interrupt.


### -param Priority [in]

A <a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_priority.md">WDF_INTERRUPT_PRIORITY</a>-typed enumerator that specifies a priority for the interrupt.


### -param TargetProcessorSet [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>-typed value that specifies a processor affinity for the interrupt, if the <i>Policy</i> parameter is set to <b>WdfIrqPolicySpecifiedProcessors</b>.


## -returns



This method does not return a value.




## -remarks



Starting in Windows Vista, drivers can specify an interrupt's priority, processor affinity, and affinity policy. For more information about how to use the registry to override the values that <b>SetPolicy</b> sets, see <a href="https://msdn.microsoft.com/e36a52d0-3a94-4017-b4a1-0b41f737523c">Interrupt Affinity and Priority</a>.


If a driver is running on an operating system version that is earlier than Windows Vista, the framework ignores the values that the driver specifies when it calls <b>SetPolicy</b>.


For more information about registry values and INF sections that specify an interrupt's priority, processor affinity, and affinity policy, see <a href="https://msdn.microsoft.com/e36a52d0-3a94-4017-b4a1-0b41f737523c">Interrupt Affinity and Priority</a>.


If a driver calls <b>SetPolicy</b>, it must do so in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff554896">IDriverEntry::OnDeviceAdd</a> callback function, after calling the <a href="https://msdn.microsoft.com/EE68BED8-5FDC-4590-8E95-B228F1DFD32D">IWDFDevice3::CreateInterrupt</a> method.

For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.


#### Examples

The following code example assigns a device interrupt to processor 0, with normal priority.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define AFFINITY_MASK(n) ((ULONG_PTR)1 &lt;&lt; (n))

pIWdfInterrupt-&gt;SetPolicy(
                          WdfIrqPolicySpecifiedProcessors,
                          WdfIrqPriorityNormal,
                          AFFINITY_MASK(0)
                          );
</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_priority.md">WDF_INTERRUPT_PRIORITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>



<a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_policy.md">WDF_INTERRUPT_POLICY</a>



<a href="..\wudfddi\nn-wudfddi-iwdfinterrupt.md">IWDFInterrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFInterrupt::SetPolicy method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

