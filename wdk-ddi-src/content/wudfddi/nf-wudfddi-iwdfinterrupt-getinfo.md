---
UID: NF:wudfddi.IWDFInterrupt.GetInfo
title: IWDFInterrupt::GetInfo
author: windows-driver-content
description: The GetInfo method retrieves information about a specified interrupt.
old-location: wdf\iwdfinterrupt_getinfo.htm
tech.root: wdf
ms.assetid: 744D0FFE-6D3C-4AED-8935-63EE9B0AFA0F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetInfo, GetInfo method, GetInfo method,IWDFInterrupt interface, IWDFInterrupt interface,GetInfo method, IWDFInterrupt.GetInfo, IWDFInterrupt::GetInfo, umdf.iwdfinterrupt_getinfo, wdf.iwdfinterrupt_getinfo, wudfddi/IWDFInterrupt::GetInfo
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
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFInterrupt.GetInfo
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

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure that the driver has previously initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh464024">WDF_INTERRUPT_INFO_INIT</a>.


## -returns



This method does not return a value.




## -remarks



The <b>GetInfo</b> method can obtain interrupt information only if your driver calls it after the framework has called the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439734">OnPrepareHardware</a> callback function and before the framework has called the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439739">OnReleaseHardware</a> callback function.

For information about the order in which a driver's callback functions are called, see <a href="https://msdn.microsoft.com/ca36eee5-482c-4cfe-a515-be9d3743e241">PnP and Power Management Scenarios in UMDF</a>.

For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.


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

WDF_INTERRUPT_INFO_INIT(&amp;Info);

pInterrupt&gt;GetInfo(&amp;Info);
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451283">IWDFInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439734">OnPrepareHardware</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439739">OnReleaseHardware</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464024">WDF_INTERRUPT_INFO_INIT</a>
 

 

