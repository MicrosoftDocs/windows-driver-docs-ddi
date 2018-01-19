---
UID: NF:filterpipeline.IFixedDocumentSequence.GetPrintTicket
title: IFixedDocumentSequence::GetPrintTicket method
author: windows-driver-content
description: The GetPrintTicket method gets the print ticket object for the fixed document sequence.
old-location: print\ifixeddocumentsequence_getprintticket.htm
old-project: print
ms.assetid: dba0ac90-a895-4daf-ba7c-b7a8a32fed19
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IFixedDocumentSequence, IFixedDocumentSequence::GetPrintTicket, GetPrintTicket
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
req.alt-api: IFixedDocumentSequence.GetPrintTicket
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

# IFixedDocumentSequence::GetPrintTicket method



## -description
The <b>GetPrintTicket</b> method gets the print ticket object for the fixed document sequence.



## -syntax

````
HRESULT GetPrintTicket(
  [out] IPartPrintTicket **ppPrintTicket
);
````


## -parameters

### -param ppPrintTicket [out]

The print ticket object for the sequence.


## -returns
<b>GetPrintTicket</b> returns an <b>HRESULT</b> value. If a print ticket is not in the fixed document sequence, <b>GetPrintTicket</b> might return E_ELEMENT_NOT_FOUND.


## -remarks
