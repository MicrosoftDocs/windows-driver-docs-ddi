---
UID: NN:filterpipeline.IFixedPage
title: IFixedPage (filterpipeline.h)
description: A filter uses the IFixedPage interface to work with fixed pages in an XPS document.
old-location: print\ifixedpage.htm
tech.root: print
ms.assetid: e9e309ed-42e5-40cc-a230-6ca001f9fb1b
ms.date: 04/20/2018
ms.keywords: IFixedPage, IFixedPage interface [Print Devices], IFixedPage interface [Print Devices],described, filterpipeline/IFixedPage, filterpipeline_4070fd54-c1df-432a-b586-a93854bf7aee.xml, print.ifixedpage
ms.topic: interface
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
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
- filterpipeline.h
api_name:
- IFixedPage
product:
- Windows
targetos: Windows
req.typenames: 
---

# IFixedPage interface


## -description


A filter uses the <b>IFixedPage</b> interface to work with fixed pages in an XPS document.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IFixedPage</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nn-filterpipeline-ipartbase">IPartBase</a>. <b>IFixedPage</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IFixedPage</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ifixedpage-deleteresource">IFixedPage::DeleteResource</a>
</td>
<td align="left" width="63%">
The <b>DeleteResource</b> method deletes a resource that is associated with the page.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ifixedpage-getpagepart">IFixedPage::GetPagePart</a>
</td>
<td align="left" width="63%">
The <b>GetPagePart</b> method gets the images, thumbnails, fonts, and so on in a page by using the URI.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ifixedpage-getprintticket">IFixedPage::GetPrintTicket</a>
</td>
<td align="left" width="63%">
The <b>GetPrintTicket</b> method gets the print ticket object for the fixed page.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ifixedpage-getwritestream">IFixedPage::GetWriteStream</a>
</td>
<td align="left" width="63%">
The <b>GetWriteStream</b> method retrieves the stream object to write page markup to  read . You can use this stream to change page markup.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ifixedpage-getxpspartiterator">IFixedPage::GetXpsPartIterator</a>
</td>
<td align="left" width="63%">
The <b>GetXpsPartIterator</b> method gets an iterator to enumerate all of the parts that are associated with the page. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ifixedpage-setpagepart">IFixedPage::SetPagePart</a>
</td>
<td align="left" width="63%">
The <b>SetPagePart</b> method associates a new part with the page.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ifixedpage-setprintticket">IFixedPage::SetPrintTicket</a>
</td>
<td align="left" width="63%">
The <b>SetPrintTicket</b> method associates a print ticket with the page.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nn-filterpipeline-ipartbase">IPartBase</a>
 

 

