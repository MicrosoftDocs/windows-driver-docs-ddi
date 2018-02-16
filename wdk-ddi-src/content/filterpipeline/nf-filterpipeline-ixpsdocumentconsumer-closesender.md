---
UID: NF:filterpipeline.IXpsDocumentConsumer.CloseSender
title: IXpsDocumentConsumer::CloseSender method
author: windows-driver-content
description: The CloseSender method tells the Pipeline Manager that the filter is done sending XPS parts.
old-location: print\ixpsdocumentconsumer_closesender.htm
old-project: print
ms.assetid: b9a860b1-d169-44b6-8dbd-0d26b050b7b0
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: CloseSender method [Print Devices], IXpsDocumentConsumer interface, filterpipeline/IXpsDocumentConsumer::CloseSender, CloseSender method [Print Devices], IXpsDocumentConsumer, IXpsDocumentConsumer interface [Print Devices], CloseSender method, CloseSender, filterpipeline_64223953-a027-45c8-b296-a07ef3340a41.xml, print.ixpsdocumentconsumer_closesender, IXpsDocumentConsumer::CloseSender
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
-	Filterpipeline.h
apiname:
-	IXpsDocumentConsumer.CloseSender
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IXpsDocumentConsumer::CloseSender method


## -description


The <code>CloseSender</code> method tells the Pipeline Manager that the filter is done sending XPS parts.


## -syntax


````
HRESULT STDMETHODCALLTYPE CloseSender(
    None
);
````


## -parameters






#### - None


## -returns



None




## -remarks



The filter must call the <code>CloseSender</code> method when it has finished sending the XPS parts to the pipeline.



