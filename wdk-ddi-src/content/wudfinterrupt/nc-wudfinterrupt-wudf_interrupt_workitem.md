---
UID: NC:wudfinterrupt.WUDF_INTERRUPT_WORKITEM
title: WUDF_INTERRUPT_WORKITEM (wudfinterrupt.h)
description: A driver's OnInterruptWorkItem event callback function processes interrupt information that the driver's OnInterruptIsr callback function has stored.
old-location: wdf\oninterruptworkitem.htm
tech.root: wdf
ms.assetid: 10677BC2-2A98-41C8-BAE9-1FA3689ACD93
ms.date: 02/26/2018
keywords: ["WUDF_INTERRUPT_WORKITEM callback function"]
ms.keywords: OnInterruptWorkItem, OnInterruptWorkItem callback function, WUDF_INTERRUPT_WORKITEM, WUDF_INTERRUPT_WORKITEM callback, umdf.oninterruptworkitem, wdf.oninterruptworkitem, wudfinterrupt/OnInterruptWorkItem
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WUDF_INTERRUPT_WORKITEM
 - wudfinterrupt/WUDF_INTERRUPT_WORKITEM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wudfinterrupt.h
api_name:
 - OnInterruptWorkItem
---

# WUDF_INTERRUPT_WORKITEM callback function


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   A driver's <i>OnInterruptWorkItem</i> event callback function processes interrupt information that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/nc-wudfinterrupt-wudf_interrupt_isr">OnInterruptIsr</a> callback function has stored.

## -parameters

### -param Interrupt 

[in]
A pointer to the interrupt object interface associated with the work item.

### -param AssociatedObject 

[in]
A pointer to the associated object.

## -remarks

To register an <i>OnInterruptWorkItem</i> callback function, your driver must place the callback function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/ns-wudfinterrupt-_wudf_interrupt_config">WUDF_INTERRUPT_CONFIG</a> structure before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createinterrupt">IWDFDevice3::CreateInterrupt</a>.

After stopping and acknowledging the interrupt, the driver should return quickly from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/nc-wudfinterrupt-wudf_interrupt_isr">OnInterruptIsr</a> callback, postponing any additional processing to a  <i>OnInterruptWorkItem</i> callback.


For more information about handling interrupts in UMDF drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-hardware-and-handling-interrupts">Accessing Hardware and Handling Interrupts</a>.


#### Examples

The function type is declared in <i>Wudfworkitem.h</i>, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
_Function_class_(WUDF_INTERRUPT_WORKITEM)
VOID
WUDF_INTERRUPT_WORKITEM(
    _In_
    IWDFInterrupt* Interrupt,
    _In_
    IWDFObject* AssociatedObject
    );

typedef WUDF_INTERRUPT_WORKITEM *PFN_WUDF_INTERRUPT_WORKITEM;</pre>
</td>
</tr>
</table></span></div>
To define an <i>OnInterruptWorkItem</i> callback function that is named <i>MyInterruptWorkItem</i>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WUDF_INTERRUPT_WORKITEM  MyInterruptWorkItem;</pre>
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
<pre>VOID
  MyInterruptWorkItem (
    _In_
    IWDFInterrupt* Interrupt,
    _In_
    IWDFObject* AssociatedObject
    )
  {…}
</pre>
</td>
</tr>
</table></span></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createinterrupt">IWDFDevice3::CreateInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/ns-wudfinterrupt-_wudf_interrupt_config">WUDF_INTERRUPT_CONFIG</a>

