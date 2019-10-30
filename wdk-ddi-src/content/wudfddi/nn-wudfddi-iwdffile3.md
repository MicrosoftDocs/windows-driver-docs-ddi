---
UID: NN:wudfddi.IWDFFile3
title: IWDFFile3 (wudfddi.h)
description: Drivers obtain the IWDFFile3 interface by calling IWDFFile::QueryInterface.
old-location: wdf\iwdffile3.htm
tech.root: wdf
ms.assetid: 67F55A00-2DE4-4ECE-8DAF-BBCBB156454E
ms.date: 02/26/2018
ms.keywords: IWDFFile3, IWDFFile3 interface, IWDFFile3 interface,described, umdf.iwdffile3, wdf.iwdffile3, wudfddi/IWDFFile3
ms.topic: interface
f1_keywords:
 - "wudfddi/IWDFFile3"
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
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IWDFFile3
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFFile3 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

Drivers obtain the <b>IWDFFile3</b> interface by calling <b>IWDFFile::QueryInterface</b>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFFile3</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile2">IWDFFile2</a>. <b>IWDFFile3</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFFile3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdffile3-getinitiatorprocessid">GetInitiatorProcessId</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdffile3-getinitiatorprocessid">GetInitiatorProcessId</a> method retrieves the initiator process ID associated with an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a> interface.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile2">IWDFFile2</a>
 

 

