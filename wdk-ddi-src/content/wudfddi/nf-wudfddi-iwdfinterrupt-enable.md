---
UID: NF:wudfddi.IWDFInterrupt.Enable
title: IWDFInterrupt::Enable (wudfddi.h)
description: The Enable method enables a specified device interrupt by calling the driver's OnInterruptEnable callback function.
old-location: wdf\iwdfinterrupt_enable.htm
tech.root: wdf
ms.assetid: 605C58C2-9A4F-4185-BB5C-95C9F5180C05
ms.date: 02/26/2018
ms.keywords: Enable, Enable method, Enable method,IWDFInterrupt interface, IWDFInterrupt interface,Enable method, IWDFInterrupt.Enable, IWDFInterrupt::Enable, umdf.iwdfinterrupt_enable, wdf.iwdfinterrupt_enable, wudfddi/IWDFInterrupt::Enable
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFInterrupt.Enable"
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
- IWDFInterrupt.Enable
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFInterrupt::Enable


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Enable</b> method enables a specified device interrupt by calling the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/nc-wudfinterrupt-wudf_interrupt_enable">OnInterruptEnable</a> callback function.


## -remarks



Most UMDF drivers do not need to call <b>IWDFInterrupt::Enable</b>, because the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/nc-wudfinterrupt-wudf_interrupt_enable">OnInterruptEnable</a> callback function each time the device enters its working (D0) state.



For more information about handling interrupts in UMDF drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-hardware-and-handling-interrupts">Accessing Hardware and Handling Interrupts</a>.


#### Examples

The following code example enables the device interrupt that is associated with a specified interrupt object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>pIWdfInterrupt->Enable();</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfinterrupt">IWDFInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfinterrupt-disable">IWDFInterrupt::Disable</a>
 

 

