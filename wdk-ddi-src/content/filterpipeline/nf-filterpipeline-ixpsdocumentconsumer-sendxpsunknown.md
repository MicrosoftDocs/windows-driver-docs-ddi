---
UID: NF:filterpipeline.IXpsDocumentConsumer.SendXpsUnknown
title: IXpsDocumentConsumer::SendXpsUnknown method
author: windows-driver-content
description: The SendXpsUnknown method sends an XPS document part that cannot be identified to the filter pipeline.
old-location: print\ixpsdocumentconsumer_sendxpsunknown.htm
old-project: print
ms.assetid: 5e2880c6-0f5a-4098-a97e-809ad75ddfd0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: SendXpsUnknown method [Print Devices], IXpsDocumentConsumer interface, IXpsDocumentConsumer::SendXpsUnknown, print.ixpsdocumentconsumer_sendxpsunknown, filterpipeline_bb57facb-5b47-4cf5-9f06-76c06d294a58.xml, IXpsDocumentConsumer interface [Print Devices], SendXpsUnknown method, IXpsDocumentConsumer, filterpipeline/IXpsDocumentConsumer::SendXpsUnknown, SendXpsUnknown method [Print Devices], SendXpsUnknown
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
-	IXpsDocumentConsumer.SendXpsUnknown
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IXpsDocumentConsumer::SendXpsUnknown method


## -description


The <code>SendXpsUnknown</code> method sends an XPS document part that cannot be identified to the filter pipeline.


## -syntax


````
HRESULT SendXpsUnknown(
  [in] IUnknown *pUnknown
);
````


## -parameters




### -param pUnknown [in]

A pointer to an unrecognized document part interface.


## -returns


<code>SendXpsUnknown</code> returns an HRE<b></b>SULT value.



## -remarks


If the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556324">IXpsDocumentProvider::GetXpsPart</a> method returns an object that the filter cannot identify, the filter should forward the unrecognized object to the next filter in the filter pipeline by calling <code>SendXpsUnknown</code>. Passing unrecognized objects to the next filter helps the filter maintain compatibility with future document formats.


