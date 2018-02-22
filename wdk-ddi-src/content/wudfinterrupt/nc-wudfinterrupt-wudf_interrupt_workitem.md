---
UID: NC:wudfinterrupt.WUDF_INTERRUPT_WORKITEM
title: WUDF_INTERRUPT_WORKITEM
author: windows-driver-content
description: A driver's OnInterruptWorkItem event callback function processes interrupt information that the driver's OnInterruptIsr callback function has stored.
old-location: wdf\oninterruptworkitem.htm
old-project: wdf
ms.assetid: 10677BC2-2A98-41C8-BAE9-1FA3689ACD93
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.oninterruptworkitem, OnInterruptWorkItem callback function, OnInterruptWorkItem, WUDF_INTERRUPT_WORKITEM, WUDF_INTERRUPT_WORKITEM, wudfinterrupt/OnInterruptWorkItem, umdf.oninterruptworkitem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wudfinterrupt.h
apiname:
-	OnInterruptWorkItem
product: Windows
targetos: Windows
req.typenames: WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, *PWUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
req.product: Windows 10 or later.
---

# WUDF_INTERRUPT_WORKITEM callback


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   A driver's <i>OnInterruptWorkItem</i> event callback function processes interrupt information that the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_isr.md">OnInterruptIsr</a> callback function has stored.


## -prototype


````
WUDF_INTERRUPT_WORKITEM OnInterruptWorkItem;

void OnInterruptWorkItem(
  _In_ IWDFInterrupt *Interrupt,
  _In_ IWDFObject    *AssociatedObject
)
{ ... }
````


## -parameters




### -param Interrupt [in]

A pointer to the interrupt object interface associated with the work item.


### -param AssociatedObject [in]

A pointer to the associated object.


## -returns



This callback function does not return a value.




## -remarks



To register an <i>OnInterruptWorkItem</i> callback function, your driver must place the callback function's address in a <a href="..\wudfinterrupt\ns-wudfinterrupt-_wudf_interrupt_config.md">WUDF_INTERRUPT_CONFIG</a> structure before calling <a href="https://msdn.microsoft.com/EE68BED8-5FDC-4590-8E95-B228F1DFD32D">IWDFDevice3::CreateInterrupt</a>.

After stopping and acknowledging the interrupt, the driver should return quickly from its <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_isr.md">OnInterruptIsr</a> callback, postponing any additional processing to a  <i>OnInterruptWorkItem</i> callback.


For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.


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

<a href="https://msdn.microsoft.com/EE68BED8-5FDC-4590-8E95-B228F1DFD32D">IWDFDevice3::CreateInterrupt</a>



<a href="..\wudfinterrupt\ns-wudfinterrupt-_wudf_interrupt_config.md">WUDF_INTERRUPT_CONFIG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WUDF_INTERRUPT_WORKITEM callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

