---
UID: NF:wudfddi.IWDFInterrupt.GetInfo
title: IWDFInterrupt::GetInfo (wudfddi.h)
description: The GetInfo method retrieves information about a specified interrupt.
old-location: wdf\iwdfinterrupt_getinfo.htm
tech.root: wdf
ms.assetid: 744D0FFE-6D3C-4AED-8935-63EE9B0AFA0F
ms.date: 02/26/2018
ms.keywords: GetInfo, GetInfo method, GetInfo method,IWDFInterrupt interface, IWDFInterrupt interface,GetInfo method, IWDFInterrupt.GetInfo, IWDFInterrupt::GetInfo, umdf.iwdfinterrupt_getinfo, wdf.iwdfinterrupt_getinfo, wudfddi/IWDFInterrupt::GetInfo
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFInterrupt.GetInfo"
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
- IWDFInterrupt.GetInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFInterrupt::GetInfo


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInfo</b> method retrieves information about a specified interrupt.


## -parameters




### -param InterruptInfo






#### - Info

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfinterrupt/ns-wudfinterrupt-_wdf_interrupt_info">WDF_INTERRUPT_INFO</a> structure that the driver has previously initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfinterrupt/nf-wudfinterrupt-wdf_interrupt_info_init">WDF_INTERRUPT_INFO_INIT</a>.


## -returns



This method does not return a value.




## -remarks



The <b>GetInfo</b> method can obtain interrupt information only if your driver calls it after the framework has called the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onpreparehardware">OnPrepareHardware</a> callback function and before the framework has called the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onreleasehardware">OnReleaseHardware</a> callback function.

For information about the order in which a driver's callback functions are called, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios-in-umdf">PnP and Power Management Scenarios in UMDF</a>.

For more information about handling interrupts in UMDF drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-hardware-and-handling-interrupts">Accessing Hardware and Handling Interrupts</a>.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
IWDFInterrupt* pInterrupt;
WDF_INTERRUPT_INFO  Info;

WDF_INTERRUPT_INFO_INIT(&Info);

pInterrupt>GetInfo(&Info);
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfinterrupt">IWDFInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onpreparehardware">OnPrepareHardware</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onreleasehardware">OnReleaseHardware</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfinterrupt/ns-wudfinterrupt-_wdf_interrupt_info">WDF_INTERRUPT_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfinterrupt/nf-wudfinterrupt-wdf_interrupt_info_init">WDF_INTERRUPT_INFO_INIT</a>
 

 

