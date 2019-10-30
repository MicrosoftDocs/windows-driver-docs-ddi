---
UID: NF:wudfddi.IWDFInterrupt.Disable
title: IWDFInterrupt::Disable (wudfddi.h)
description: The Disable method disables a specified device interrupt by calling the driver's OnInterruptDisable callback function.
old-location: wdf\iwdfinterrupt_disable.htm
tech.root: wdf
ms.assetid: D87C868D-9538-4752-AEBD-2A15E53628CF
ms.date: 02/26/2018
ms.keywords: Disable, Disable method, Disable method,IWDFInterrupt interface, IWDFInterrupt interface,Disable method, IWDFInterrupt.Disable, IWDFInterrupt::Disable, umdf.iwdfinterrupt_disable, wdf.iwdfinterrupt_disable, wudfddi/IWDFInterrupt::Disable
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFInterrupt.Disable"
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
- IWDFInterrupt.Disable
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFInterrupt::Disable


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Disable</b> method disables a specified device interrupt by calling the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/nc-wudfinterrupt-wudf_interrupt_disable">OnInterruptDisable</a> callback function.


## -parameters






## -returns



This method does not return a value.




## -remarks



Most UMDF drivers do not need to call <b>IWDFInterrupt::Disable</b>, because the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/nc-wudfinterrupt-wudf_interrupt_disable">OnInterruptDisable</a> callback function each time the device leaves its working (D0) state.



For more information about handling interrupts in UMDF drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-hardware-and-handling-interrupts">Accessing Hardware and Handling Interrupts</a>.


#### Examples

The following code example disables the device interrupt that is associated with a specified interrupt object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>pIWdfInterrupt->Disable();</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfinterrupt">IWDFInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfinterrupt-enable">IWDFInterrupt::Enable</a>
 

 

