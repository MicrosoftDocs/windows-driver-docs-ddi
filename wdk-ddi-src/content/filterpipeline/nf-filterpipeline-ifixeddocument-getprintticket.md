---
UID: NF:filterpipeline.IFixedDocument.GetPrintTicket
title: IFixedDocument::GetPrintTicket method
author: windows-driver-content
description: The GetPrintTicket method gets the print ticket object for the fixed document.
old-location: print\ifixeddocument_getprintticket.htm
old-project: print
ms.assetid: b9c4768e-8292-4311-b64a-ac1ef7d2ad10
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: GetPrintTicket method [Print Devices], IFixedDocument interface, print.ifixeddocument_getprintticket, filterpipeline_4da54cb5-31ab-47b3-b2a6-7485e344f233.xml, GetPrintTicket method [Print Devices], filterpipeline/IFixedDocument::GetPrintTicket, IFixedDocument interface [Print Devices], GetPrintTicket method, IFixedDocument, GetPrintTicket, IFixedDocument::GetPrintTicket
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: filterpipeline.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	filterpipeline.h
apiname:
-	IFixedDocument.GetPrintTicket
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IFixedDocument::GetPrintTicket method


## -description


The <b>GetPrintTicket</b> method gets the print ticket object for the fixed document.


## -syntax


````
HRESULT GetPrintTicket(
  [out] IPartPrintTicket **ppPrintTicket
);
````


## -parameters




### -param ppPrintTicket [out]

The print ticket object for the fixed document.


## -returns


<b>GetPrintTicket</b> returns an <b>HRESULT</b> value. If a print ticket is not in the fixed document, this method might return E_ELEMENT_NOT_FOUND.


