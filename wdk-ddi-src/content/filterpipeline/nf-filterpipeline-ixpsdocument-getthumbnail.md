---
UID: NF:filterpipeline.IXpsDocument.GetThumbnail
title: IXpsDocument::GetThumbnail method
author: windows-driver-content
description: The GetThumbnail method gets the document thumbnail object.
old-location: print\ixpsdocument_getthumbnail.htm
old-project: print
ms.assetid: 74466609-4408-4065-a607-cd338902335d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetThumbnail method [Print Devices], GetThumbnail method [Print Devices], IXpsDocument interface, GetThumbnail,IXpsDocument.GetThumbnail, IXpsDocument, IXpsDocument interface [Print Devices], GetThumbnail method, IXpsDocument::GetThumbnail, filterpipeline/IXpsDocument::GetThumbnail, filterpipeline_dbbd8b80-198b-4cdd-af97-68093d87c4e1.xml, print.ixpsdocument_getthumbnail
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
-	IXpsDocument.GetThumbnail
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IXpsDocument::GetThumbnail method


## -description


The <code>GetThumbnail</code> method gets the document thumbnail object. 


## -syntax


````
HRESULT GetThumbnail(
  [out] IPartThumbnail **ppThumbnail
);
````


## -parameters




### -param ppThumbnail [out]

The thumbnail object in the document.


## -returns



<code>GetThumbnail</code> returns an <b>HRESULT</b> value. This method might return E_ELEMENT_NOT_FOUND if a thumbnail cannot be found.



