---
UID: NN:wudfddi.IWDFWorkItem
title: IWDFWorkItem
author: windows-driver-content
description: This interface exposes a work item object.
old-location: wdf\iwdfworkitem.htm
old-project: wdf
ms.assetid: F9EDA26E-92E0-4936-87B7-E1E2A02A9D96
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFWorkItem, IWDFWorkItem interface, IWDFWorkItem interface, described, umdf.iwdfworkitem, wdf.iwdfworkitem, wudfddi/IWDFWorkItem
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IWDFWorkItem
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFWorkItem interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

This interface exposes a work item object.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFWorkItem</b> interface inherits from <a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>. <b>IWDFWorkItem</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFWorkItem</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh463883">Enqueue</a>
</td>
<td align="left" width="63%">

   The <a href="https://msdn.microsoft.com/library/windows/hardware/hh463883">Enqueue</a> method adds this interface's framework work-item object to the system's work-item queue.
  

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh463886">Flush</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh463886">Flush</a> method returns after this interface's work item has been serviced.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh463891">GetParentObject</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh463891">GetParentObject</a> method returns the parent framework object of this interface's  work item.

</td>
</tr>
</table> 


## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFWorkItem interface%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

