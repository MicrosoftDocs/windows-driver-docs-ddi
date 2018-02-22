---
UID: NF:filterpipeline.IXpsDocumentConsumer.GetNewEmptyPart
title: IXpsDocumentConsumer::GetNewEmptyPart method
author: windows-driver-content
description: The GetNewEmptyPart method creates a new XPS part.
old-location: print\ixpsdocumentconsumer_getnewemptypart.htm
old-project: print
ms.assetid: cc0911da-46ca-4cf7-a59e-da0d53e1d10c
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: GetNewEmptyPart method [Print Devices], filterpipeline/IXpsDocumentConsumer::GetNewEmptyPart, print.ixpsdocumentconsumer_getnewemptypart, IXpsDocumentConsumer interface [Print Devices], GetNewEmptyPart method, IXpsDocumentConsumer::GetNewEmptyPart, GetNewEmptyPart method [Print Devices], IXpsDocumentConsumer interface, GetNewEmptyPart, filterpipeline_c4770528-f57a-4197-b60b-5b780d5e7752.xml, IXpsDocumentConsumer
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
-	IXpsDocumentConsumer.GetNewEmptyPart
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IXpsDocumentConsumer::GetNewEmptyPart method


## -description


The <code>GetNewEmptyPart</code> method creates a new XPS part.


## -syntax


````
HRESULT GetNewEmptyPart(
  [in]  const wchar_t           *uri,
  [in]        REFIID            riid,
  [out]       void              **ppNewObject,
  [out]       IPrintWriteStream **ppWriteStream
);
````


## -parameters




### -param uri [in]

The URI for the new part to be created.


### -param riid [in]

A reference identifier (REFIID) for one of the following interfaces: 

<ul>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ifixeddocument.md">IFixedDocument</a>


</li>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ifixedpage.md">IFixedPage</a>


</li>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ipartimage.md">IPartImage</a>


</li>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ipartthumbnail.md">IPartThumbnail</a>


</li>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ipartfont.md">IPartFont</a>


</li>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ipartprintticket.md">IPartPrintTicket</a>


</li>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ipartcolorprofile.md">IPartColorProfile</a>


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

<a href="..\filterpipeline\nn-filterpipeline-ifixedpage.md">IFixedPage</a>



<a href="..\filterpipeline\nn-filterpipeline-ixpsdocumentconsumer.md">IXpsDocumentConsumer</a>



<a href="..\filterpipeline\nn-filterpipeline-ipartfont.md">IPartFont</a>



<a href="..\filterpipeline\nn-filterpipeline-ipartimage.md">IPartImage</a>



<a href="..\filterpipeline\nn-filterpipeline-ipartprintticket.md">IPartPrintTicket</a>



<a href="..\filterpipeline\nn-filterpipeline-ifixeddocument.md">IFixedDocument</a>



<a href="..\filterpipeline\nn-filterpipeline-ipartthumbnail.md">IPartThumbnail</a>



<a href="..\filterpipeline\nn-filterpipeline-ipartcolorprofile.md">IPartColorProfile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IXpsDocumentConsumer::GetNewEmptyPart method%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

