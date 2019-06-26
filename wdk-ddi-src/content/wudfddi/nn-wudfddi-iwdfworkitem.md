---
UID: NN:wudfddi.IWDFWorkItem
title: IWDFWorkItem (wudfddi.h)
description: This interface exposes a work item object.
old-location: wdf\iwdfworkitem.htm
tech.root: wdf
ms.assetid: F9EDA26E-92E0-4936-87B7-E1E2A02A9D96
ms.date: 02/26/2018
ms.keywords: IWDFWorkItem, IWDFWorkItem interface, IWDFWorkItem interface,described, umdf.iwdfworkitem, wdf.iwdfworkitem, wudfddi/IWDFWorkItem
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFWorkItem interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

This interface exposes a work item object.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFWorkItem</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>. <b>IWDFWorkItem</b> also has these types of members:
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfworkitem-enqueue">Enqueue</a>
</td>
<td align="left" width="63%">

   The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfworkitem-enqueue">Enqueue</a> method adds this interface's framework work-item object to the system's work-item queue.
  

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfworkitem-flush">Flush</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfworkitem-flush">Flush</a> method returns after this interface's work item has been serviced.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfworkitem-getparentobject">GetParentObject</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfworkitem-getparentobject">GetParentObject</a> method returns the parent framework object of this interface's  work item.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>
 

 

