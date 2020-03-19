---
UID: NF:filterpipeline.IXpsDocument.GetThumbnail
title: IXpsDocument::GetThumbnail (filterpipeline.h)
description: The GetThumbnail method gets the document thumbnail object.
old-location: print\ixpsdocument_getthumbnail.htm
tech.root: print
ms.assetid: 74466609-4408-4065-a607-cd338902335d
ms.date: 04/20/2018
keywords: ["IXpsDocument::GetThumbnail"]
ms.keywords: GetThumbnail, GetThumbnail method [Print Devices], GetThumbnail method [Print Devices],IXpsDocument interface, IXpsDocument interface [Print Devices],GetThumbnail method, IXpsDocument.GetThumbnail, IXpsDocument::GetThumbnail, filterpipeline/IXpsDocument::GetThumbnail, filterpipeline_dbbd8b80-198b-4cdd-af97-68093d87c4e1.xml, print.ixpsdocument_getthumbnail
f1_keywords:
 - "filterpipeline/IXpsDocument.GetThumbnail"
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
- IXpsDocument.GetThumbnail
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsDocument::GetThumbnail


## -description


The <code>GetThumbnail</code> method gets the document thumbnail object. 


## -parameters




### -param ppThumbnail [out]

The thumbnail object in the document.


## -returns



<code>GetThumbnail</code> returns an <b>HRESULT</b> value. This method might return E_ELEMENT_NOT_FOUND if a thumbnail cannot be found.



