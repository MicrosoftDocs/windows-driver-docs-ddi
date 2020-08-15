---
UID: NC:wudfinterrupt.WUDF_INTERRUPT_ISR
title: WUDF_INTERRUPT_ISR (wudfinterrupt.h)
description: A driver's OnInterruptIsr event callback function services a hardware interrupt.
old-location: wdf\oninterruptisr.htm
tech.root: wdf
ms.assetid: D4B8182A-67A5-4D64-A95C-5EB6A1C1E4F0
ms.date: 02/26/2018
keywords: ["WUDF_INTERRUPT_ISR callback function"]
ms.keywords: OnInterruptIsr, OnInterruptIsr callback function, WUDF_INTERRUPT_ISR, WUDF_INTERRUPT_ISR callback, umdf.oninterruptisr, wdf.oninterruptisr, wudfinterrupt/OnInterruptIsr
f1_keywords:
 - "wudfinterrupt/OnInterruptIsr"
 - "OnInterruptIsr"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wudfinterrupt.h
api_name:
- OnInterruptIsr
targetos: Windows
req.typenames: 
---

# WUDF_INTERRUPT_ISR callback function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <i>OnInterruptIsr</i> event callback function services a hardware interrupt.

## -syntax

```cpp
typedef
BOOLEAN
_Function_class_(WUDF_INTERRUPT_ISR)
WUDF_INTERRUPT_ISR(
    _In_
    IWDFInterrupt* Interrupt,
    _In_
    ULONG MessageID,
    _In_
    ULONG Reserved
    );

typedef WUDF_INTERRUPT_ISR *PFN_WUDF_INTERRUPT_ISR;
```

## -parameters




### -param Interrupt


### -param MessageID 
[in]
If the device is using message-signaled interrupts (MSIs), this parameter is the message number that identifies the device's hardware interrupt message. Otherwise, this value is 0.


### -param Reserved 
[in]
Reserved for system use.


#### - pInterrupt [in]

A pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfinterrupt">IWDFInterrupt</a> interface.






## -remarks

Returns TRUE if the driver acknowledges ownership of the interrupt, and has stopped and acknowledged the interrupt on its device. Otherwise, returns FALSE.


To register an <i>OnInterruptIsr</i> callback function, your driver must place the callback function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/ns-wudfinterrupt-_wudf_interrupt_config">WUDF_INTERRUPT_CONFIG</a> structure before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createinterrupt">IWDFDevice3::CreateInterrupt</a>.


The <i>OnInterruptIsr</i> callback function is a UMDF driver's interrupt service routine (ISR), which is called at PASSIVE_LEVEL when a hardware interrupt occurs.

For an edge-triggered interrupt or message-signaled interrupt (MSI), the framework calls <i>OnInterruptIsr</i> outside of the operating system's interrupt dispatch context. This is because UMDF allows only non-shared edge-triggered or MSI interrupts, and the driver does not need to interact with its hardware within this context.

For a level-triggered interrupt, the framework calls <i>OnInterruptIsr</i> in the context of the operating system's interrupt dispatch. As a result, the operating system's interrupt dispatch thread is blocked in kernel-mode waiting for a response from the driver.

Typically, <i>OnInterruptIsr</i> saves any volatile information that might be lost and clears the hardware interrupt. For a level-triggered interrupt, the driver should stop and acknowledge the interrupt on the device and then return TRUE if it owns the interrupt. The driver should do any further processing in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/nc-wudfinterrupt-wudf_interrupt_workitem">OnInterruptWorkItem</a> callback. To queue a work item, the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfinterrupt-queueworkitemforisr">IWDFInterrupt::QueueWorkItemForIsr</a> method.


For more information about handling interrupts in UMDF drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-hardware-and-handling-interrupts">Accessing Hardware and Handling Interrupts</a>.


#### Examples

The function type is declared in <i>Wudfinterrupt.h</i>, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
BOOLEAN
WUDF_INTERRUPT_ISR(
    _In_
    IWDFInterrupt* Interrupt,
    _In_
    ULONG MessageID,
    _In_
    ULONG Reserved
    );

typedef WUDF_INTERRUPT_ISR *PFN_WUDF_INTERRUPT_ISR;</pre>
</td>
</tr>
</table></span></div>
To define an <i>OnInterruptIsr</i> callback function that is named <i>MyInterruptIsr</i>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WUDF_INTERRUPT_NOTIFY  MyInterruptIsr;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN
  MyInterruptIsr (
    IN IWDFInterrupt*  pInterrupt,
    IN ULONG  MessageID,
    IN ULONG Reserved
    )
  {…}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createinterrupt">IWDFDevice3::CreateInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/nc-wudfinterrupt-wudf_interrupt_workitem">OnInterruptWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/ns-wudfinterrupt-_wudf_interrupt_config">WUDF_INTERRUPT_CONFIG</a>
 

 

