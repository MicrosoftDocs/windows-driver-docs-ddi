---
UID: NF:filterpipeline.IXpsDocumentConsumer.CloseSender
title: IXpsDocumentConsumer::CloseSender (filterpipeline.h)
description: The CloseSender method tells the Pipeline Manager that the filter is done sending XPS parts.
old-location: print\ixpsdocumentconsumer_closesender.htm
tech.root: print
ms.assetid: b9a860b1-d169-44b6-8dbd-0d26b050b7b0
ms.date: 04/20/2018
keywords: ["IXpsDocumentConsumer::CloseSender"]
ms.keywords: CloseSender, CloseSender method [Print Devices], CloseSender method [Print Devices],IXpsDocumentConsumer interface, IXpsDocumentConsumer interface [Print Devices],CloseSender method, IXpsDocumentConsumer.CloseSender, IXpsDocumentConsumer::CloseSender, filterpipeline/IXpsDocumentConsumer::CloseSender, filterpipeline_64223953-a027-45c8-b296-a07ef3340a41.xml, print.ixpsdocumentconsumer_closesender
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
 - IXpsDocumentConsumer::CloseSender
 - filterpipeline/IXpsDocumentConsumer::CloseSender
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Filterpipeline.h
api_name:
 - IXpsDocumentConsumer.CloseSender
---

# IXpsDocumentConsumer::CloseSender


## -description

The <code>CloseSender</code> method tells the Pipeline Manager that the filter is done sending XPS parts.

## -returns

None

## -remarks

The filter must call the <code>CloseSender</code> method when it has finished sending the XPS parts to the pipeline.

