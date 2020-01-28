---
UID: NF:filterpipeline.IXpsDocumentConsumer.SendXpsUnknown
title: IXpsDocumentConsumer::SendXpsUnknown (filterpipeline.h)
description: The SendXpsUnknown method sends an XPS document part that cannot be identified to the filter pipeline.
old-location: print\ixpsdocumentconsumer_sendxpsunknown.htm
tech.root: print
ms.assetid: 5e2880c6-0f5a-4098-a97e-809ad75ddfd0
ms.date: 04/20/2018
ms.keywords: IXpsDocumentConsumer interface [Print Devices],SendXpsUnknown method, IXpsDocumentConsumer.SendXpsUnknown, IXpsDocumentConsumer::SendXpsUnknown, SendXpsUnknown, SendXpsUnknown method [Print Devices], SendXpsUnknown method [Print Devices],IXpsDocumentConsumer interface, filterpipeline/IXpsDocumentConsumer::SendXpsUnknown, filterpipeline_bb57facb-5b47-4cf5-9f06-76c06d294a58.xml, print.ixpsdocumentconsumer_sendxpsunknown
f1_keywords:
 - "filterpipeline/IXpsDocumentConsumer.SendXpsUnknown"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- filterpipeline.h
api_name:
- IXpsDocumentConsumer.SendXpsUnknown
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsDocumentConsumer::SendXpsUnknown


## -description


The <code>SendXpsUnknown</code> method sends an XPS document part that cannot be identified to the filter pipeline.


## -parameters




### -param pUnknown [in]

A pointer to an unrecognized document part interface.


## -returns



<code>SendXpsUnknown</code> returns an HRE<b></b>SULT value.




## -remarks



If the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-ixpsdocumentprovider-getxpspart">IXpsDocumentProvider::GetXpsPart</a> method returns an object that the filter cannot identify, the filter should forward the unrecognized object to the next filter in the filter pipeline by calling <code>SendXpsUnknown</code>. Passing unrecognized objects to the next filter helps the filter maintain compatibility with future document formats.



