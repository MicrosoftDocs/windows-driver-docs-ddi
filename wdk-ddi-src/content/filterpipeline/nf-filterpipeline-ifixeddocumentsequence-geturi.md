---
UID: NF:filterpipeline.IFixedDocumentSequence.GetUri
title: IFixedDocumentSequence::GetUri method
author: windows-driver-content
description: The GetUri method gets the URI of the fixed document sequence.
old-location: print\ifixeddocumentsequence_geturi.htm
old-project: print
ms.assetid: 45017249-2ea5-43f6-9712-787f52cb6e4b
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: IFixedDocumentSequence, GetUri, print.ifixeddocumentsequence_geturi, GetUri method [Print Devices], IFixedDocumentSequence interface, IFixedDocumentSequence interface [Print Devices], GetUri method, GetUri method [Print Devices], filterpipeline/IFixedDocumentSequence::GetUri, filterpipeline_6d286919-21a8-40e8-8c6b-dd035ffe0ae1.xml, IFixedDocumentSequence::GetUri
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
-	IFixedDocumentSequence.GetUri
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IFixedDocumentSequence::GetUri method


## -description


The <b>GetUri</b> method gets the URI of the fixed document sequence.


## -syntax


````
HRESULT GetUri(
  [out] BSTR *uri
);
````


## -parameters




### -param uri [out]

The URI of the fixed document sequence.


## -returns



<b>GetUri</b> returns an <b>HRESULT</b> value.



