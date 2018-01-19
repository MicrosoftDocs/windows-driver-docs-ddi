---
UID: NF:filterpipeline.IFixedPage.GetPrintTicket
title: IFixedPage::GetPrintTicket method
author: windows-driver-content
description: The GetPrintTicket method gets the print ticket object for the fixed page.
old-location: print\ifixedpage_getprintticket.htm
old-project: print
ms.assetid: 4a30efd9-8fef-4fef-8293-b7df5b954977
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IFixedPage, IFixedPage::GetPrintTicket, GetPrintTicket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IFixedPage.GetPrintTicket
req.alt-loc: filterpipeline.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: EXpsFontRestriction
---

# IFixedPage::GetPrintTicket method



## -description
The <b>GetPrintTicket</b> method gets the print ticket object for the fixed page.



## -syntax

````
HRESULT GetPrintTicket(
  [out] IPartPrintTicket **ppPrintTicket
);
````


## -parameters

### -param ppPrintTicket [out]

Pointer to a location into which the method writes a pointer to the <a href="..\filterpipeline\nn-filterpipeline-ipartprintticket.md">IPartPrintTicket</a> interface of a print ticket object. This object contains the print ticket for the fixed page.


## -returns
<b>GetPrintTicket</b> returns an <b>HRESULT</b> value. If a print ticket is not in the fixed page, <b>GetPrintTicket</b> might return E_ELEMENT_NOT_FOUND.


## -remarks
After calling this method to get the page-level print ticket, a print driver filter can obtain the <i>effective</i> print ticket for the fixed page by merging the page-level print ticket with the document-level print ticket and the job-level print ticket. The filter can get the document-level and job-level print tickets by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550992">IFixedDocument::GetPrintTicket</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550977">IFixedDocumentSequence::GetPrintTicket</a> methods. For more information about merging print tickets, see <a href="https://msdn.microsoft.com/2d9cf4d3-5c73-4355-b5e0-effcfb7102cc">Print Ticket Merging</a>.


## -see-also
<dl>
<dt>
<a href="..\filterpipeline\nn-filterpipeline-ifixedpage.md">IFixedPage</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550992">IFixedDocument::GetPrintTicket</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550977">IFixedDocumentSequence::GetPrintTicket</a>
</dt>
<dt>
<a href="..\filterpipeline\nn-filterpipeline-ipartprintticket.md">IPartPrintTicket</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IFixedPage::GetPrintTicket method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

