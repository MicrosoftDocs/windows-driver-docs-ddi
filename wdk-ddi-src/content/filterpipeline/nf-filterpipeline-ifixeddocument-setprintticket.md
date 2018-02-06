---
UID: NF:filterpipeline.IFixedDocument.SetPrintTicket
title: IFixedDocument::SetPrintTicket method
author: windows-driver-content
description: The SetPrintTicket method inserts a print ticket into the fixed document.
old-location: print\ifixeddocument_setprintticket.htm
old-project: print
ms.assetid: 701c53d5-bb1e-4003-9505-19b9c46689c6
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: filterpipeline/IFixedDocument::SetPrintTicket, SetPrintTicket method [Print Devices], print.ifixeddocument_setprintticket, IFixedDocument interface [Print Devices], SetPrintTicket method, SetPrintTicket method [Print Devices], IFixedDocument interface, filterpipeline_96d89fc9-899f-4ede-8da5-898471f6b769.xml, SetPrintTicket, IFixedDocument::SetPrintTicket, IFixedDocument
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
-	IFixedDocument.SetPrintTicket
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IFixedDocument::SetPrintTicket method


## -description


The <b>SetPrintTicket</b> method inserts a print ticket into the fixed document.


## -syntax


````
HRESULT SetPrintTicket(
  [in] IPartPrintTicket *pPrintTicket
);
````


## -parameters




### -param pPrintTicket [in]

A pointer to the print ticket to be inserted.


## -returns


<b>SetPrintTicket</b> returns an <b>HRESULT</b> value.


