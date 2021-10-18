---
UID: NN:filterpipeline.IXpsDocumentProvider
title: IXpsDocumentProvider (filterpipeline.h)
description: The IxpsDocumentProvider interface provides interfaces to consume parts of a document.
tech.root: print
ms.date: 06/11/2021
keywords: ["IXpsDocumentProvider interface"]
ms.keywords: IXpsDocumentProvider, IXpsDocumentProvider interface [Print Devices], IXpsDocumentProvider interface [Print Devices],described, filterpipeline/IXpsDocumentProvider, filterpipeline_5c7b0fb9-f191-47c7-b0fc-96371c21f993.xml, print.ixpsdocumentprovider
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
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
 - IXpsDocumentProvider
 - filterpipeline/IXpsDocumentProvider
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IXpsDocumentProvider
---

# IXpsDocumentProvider interface

## -description

The **IxpsDocumentProvider** interface provides interfaces to consume parts of a document.

> [!NOTE]
> The XPS print filter pipeline does not preserve digital signatures or story fragments. You may be able to work around this by using stream filters.

## -inheritance

The **IXpsDocumentProvider** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.
