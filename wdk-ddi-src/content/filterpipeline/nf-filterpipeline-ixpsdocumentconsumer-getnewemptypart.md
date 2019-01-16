---
UID: NF:filterpipeline.IXpsDocumentConsumer.GetNewEmptyPart
title: IXpsDocumentConsumer::GetNewEmptyPart
description: The GetNewEmptyPart method creates a new XPS part.
old-location: print\ixpsdocumentconsumer_getnewemptypart.htm
tech.root: print
ms.assetid: cc0911da-46ca-4cf7-a59e-da0d53e1d10c
ms.date: 04/20/2018
ms.keywords: GetNewEmptyPart, GetNewEmptyPart method [Print Devices], GetNewEmptyPart method [Print Devices],IXpsDocumentConsumer interface, IXpsDocumentConsumer interface [Print Devices],GetNewEmptyPart method, IXpsDocumentConsumer.GetNewEmptyPart, IXpsDocumentConsumer::GetNewEmptyPart, filterpipeline/IXpsDocumentConsumer::GetNewEmptyPart, filterpipeline_c4770528-f57a-4197-b60b-5b780d5e7752.xml, print.ixpsdocumentconsumer_getnewemptypart
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IXpsDocumentConsumer.GetNewEmptyPart
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsDocumentConsumer::GetNewEmptyPart


## -description


The <code>GetNewEmptyPart</code> method creates a new XPS part.


## -parameters




### -param uri [in]

The URI for the new part to be created.


### -param riid [in]

A reference identifier (REFIID) for one of the following interfaces: 

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550966">IFixedDocument</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551019">IFixedPage</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551906">IPartImage</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551939">IPartThumbnail</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551887">IPartFont</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551924">IPartPrintTicket</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551874">IPartColorProfile</a>


</li>
</ul>

### -param ppNewObject [out]

A pointer to the new object to be created.


### -param ppWriteStream [out]

A data stream object that the part will be written to. Each part is associated with a data stream object.


## -returns



<code>GetNewEmptyPart</code> returns an <b>HRESULT</b>.




## -remarks



A filter can create new XPS parts by using the <code>GetNewEmptyPart</code> method. Typically, the filter receives XPS parts from the inter-filter object.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550966">IFixedDocument</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551019">IFixedPage</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551874">IPartColorProfile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551887">IPartFont</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551906">IPartImage</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551924">IPartPrintTicket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551939">IPartThumbnail</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556291">IXpsDocumentConsumer</a>
 

 

