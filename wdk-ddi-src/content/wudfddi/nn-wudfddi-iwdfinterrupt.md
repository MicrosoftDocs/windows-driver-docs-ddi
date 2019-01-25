---
UID: NN:wudfddi.IWDFInterrupt
title: IWDFInterrupt (wudfddi.h)
description: This interface exposes an interrupt object.
old-location: wdf\iwdfinterrupt.htm
tech.root: wdf
ms.assetid: 729A2361-6FE1-4096-AC8B-3D042326EE5C
ms.date: 02/26/2018
ms.keywords: IWDFInterrupt, IWDFInterrupt interface, IWDFInterrupt interface,described, umdf.iwdfinterrupt, wdf.iwdfinterrupt, wudfddi/IWDFInterrupt
ms.topic: interface
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
-	IWDFInterrupt
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFInterrupt interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

This interface exposes an interrupt object.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFInterrupt</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff560200">IWDFObject</a>. <b>IWDFInterrupt</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFInterrupt</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451289">AcquireInterruptLock</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451289">AcquireInterruptLock</a> method begins a code sequence that executes while holding an interrupt object's lock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450971">Disable</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh450971">Disable</a> method disables a specified device interrupt by calling the driver's <a href="https://msdn.microsoft.com/3ADBD4C2-075E-4988-BF13-EB0C3E0C02BF">OnInterruptDisable</a> callback function.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451004">Enable</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451004">Enable</a> method enables a specified device interrupt by calling the driver's <a href="https://msdn.microsoft.com/6C091427-59FF-4101-ACD6-353C959794F6">OnInterruptEnable</a> callback function.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451305">GetDevice</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451305">GetDevice</a> method returns the framework device object interface for this interrupt object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451309">GetInfo</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451309">GetInfo</a> method retrieves information about a specified interrupt.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451314">QueueWorkItemForIsr</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451314">QueueWorkItemForIsr</a> method queues a work item to process interrupt-related work outside of the interrupt service routine.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451319">ReleaseInterruptLock</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451319">ReleaseInterruptLock</a> method ends a code sequence that executes while holding an interrupt object's lock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451324">SetExtendedPolicy</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451324">SetExtendedPolicy</a> method specifies the interrupt priority, processor affinity, affinity policy, and processor group for a specified interrupt.
  

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451328">SetPolicy</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451328">SetPolicy</a> method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451332">TryToAcquireInterruptLock</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451332">TryToAcquireInterruptLock</a> method acquires the interrupt lock if no other thread has already acquired it.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560200">IWDFObject</a>
 

 

