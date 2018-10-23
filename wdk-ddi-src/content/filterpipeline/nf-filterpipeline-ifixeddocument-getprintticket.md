---
UID: NF:filterpipeline.IFixedDocument.GetPrintTicket
title: IFixedDocument::GetPrintTicket
author: windows-driver-content
description: The GetPrintTicket method gets the print ticket object for the fixed document.
old-location: print\ifixeddocument_getprintticket.htm
tech.root: print
ms.assetid: b9c4768e-8292-4311-b64a-ac1ef7d2ad10
ms.date: 04/20/2018
ms.keywords: GetPrintTicket, GetPrintTicket method [Print Devices], GetPrintTicket method [Print Devices],IFixedDocument interface, IFixedDocument interface [Print Devices],GetPrintTicket method, IFixedDocument.GetPrintTicket, IFixedDocument::GetPrintTicket, filterpipeline/IFixedDocument::GetPrintTicket, filterpipeline_4da54cb5-31ab-47b3-b2a6-7485e344f233.xml, print.ifixeddocument_getprintticket
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IFixedDocument.GetPrintTicket
product:
- Windows
targetos: Windows
req.typenames: 
---

# IFixedDocument::GetPrintTicket


## -description


The <b>GetPrintTicket</b> method gets the print ticket object for the fixed document.


## -parameters




### -param ppPrintTicket [out]

The print ticket object for the fixed document.


## -returns



<b>GetPrintTicket</b> returns an <b>HRESULT</b> value. If a print ticket is not in the fixed document, this method might return E_ELEMENT_NOT_FOUND.



