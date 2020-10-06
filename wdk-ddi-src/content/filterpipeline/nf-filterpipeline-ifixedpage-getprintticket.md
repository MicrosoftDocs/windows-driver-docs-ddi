---
UID: NF:filterpipeline.IFixedPage.GetPrintTicket
title: IFixedPage::GetPrintTicket (filterpipeline.h)
description: The GetPrintTicket method gets the print ticket object for the fixed page.
old-location: print\ifixedpage_getprintticket.htm
tech.root: print
ms.assetid: 4a30efd9-8fef-4fef-8293-b7df5b954977
ms.date: 04/20/2018
keywords: ["IFixedPage::GetPrintTicket"]
ms.keywords: GetPrintTicket, GetPrintTicket method [Print Devices], GetPrintTicket method [Print Devices],IFixedPage interface, IFixedPage interface [Print Devices],GetPrintTicket method, IFixedPage.GetPrintTicket, IFixedPage::GetPrintTicket, filterpipeline/IFixedPage::GetPrintTicket, filterpipeline_13ccb2a1-7898-41d1-b11f-55ca3cc881ab.xml, print.ifixedpage_getprintticket
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IFixedPage::GetPrintTicket
 - filterpipeline/IFixedPage::GetPrintTicket
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IFixedPage.GetPrintTicket
---

# IFixedPage::GetPrintTicket


## -description

The <b>GetPrintTicket</b> method gets the print ticket object for the fixed page.

## -parameters

### -param ppPrintTicket 

[out]
Pointer to a location into which the method writes a pointer to the <a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-ipartprintticket">IPartPrintTicket</a> interface of a print ticket object. This object contains the print ticket for the fixed page.

## -returns

<b>GetPrintTicket</b> returns an <b>HRESULT</b> value. If a print ticket is not in the fixed page, <b>GetPrintTicket</b> might return E_ELEMENT_NOT_FOUND.

## -remarks

After calling this method to get the page-level print ticket, a print driver filter can obtain the <i>effective</i> print ticket for the fixed page by merging the page-level print ticket with the document-level print ticket and the job-level print ticket. The filter can get the document-level and job-level print tickets by calling the <a href="/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-ifixeddocument-getprintticket">IFixedDocument::GetPrintTicket</a> and <a href="/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-ifixeddocumentsequence-getprintticket">IFixedDocumentSequence::GetPrintTicket</a> methods. For more information about merging print tickets, see <a href="/windows-hardware/drivers/print/print-ticket-merging">Print Ticket Merging</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-ifixeddocument-getprintticket">IFixedDocument::GetPrintTicket</a>



<a href="/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-ifixeddocumentsequence-getprintticket">IFixedDocumentSequence::GetPrintTicket</a>



<a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-ifixedpage">IFixedPage</a>



<a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-ipartprintticket">IPartPrintTicket</a>