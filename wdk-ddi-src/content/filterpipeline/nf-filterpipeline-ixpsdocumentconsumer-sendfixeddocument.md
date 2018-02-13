---
UID: NF:filterpipeline.IXpsDocumentConsumer.SendFixedDocument
title: IXpsDocumentConsumer::SendFixedDocument method
author: windows-driver-content
description: The SendFixedDocument method sends a fixed document object to the pipeline.
old-location: print\ixpsdocumentconsumer_sendfixeddocument.htm
old-project: print
ms.assetid: 917dd9c3-5552-43d0-b396-9ba236f53132
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: IXpsDocumentConsumer::SendFixedDocument, SendFixedDocument, SendFixedDocument method [Print Devices], IXpsDocumentConsumer interface, IXpsDocumentConsumer interface [Print Devices], SendFixedDocument method, IXpsDocumentConsumer, SendFixedDocument method [Print Devices], filterpipeline/IXpsDocumentConsumer::SendFixedDocument, filterpipeline_a6ecc63d-889e-4ae1-8031-16accffa9c2a.xml, print.ixpsdocumentconsumer_sendfixeddocument
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
-	IXpsDocumentConsumer.SendFixedDocument
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IXpsDocumentConsumer::SendFixedDocument method


## -description


The <code>SendFixedDocument</code> method sends a fixed document object to the pipeline.


## -syntax


````
HRESULT SendFixedDocument(
  [in] IFixedDocument *pIFixedDocument
);
````


## -parameters




### -param pIFixedDocument [in]

A pointer to an XPS fixed document object.


## -returns



<code>SendFixedDocument</code> returns an <b>HRESULT</b> value.



