---
UID: NF:filterpipeline.IFixedPage.SetPagePart
title: IFixedPage::SetPagePart method
author: windows-driver-content
description: The SetPagePart method associates a new part with the page.
old-location: print\ifixedpage_setpagepart.htm
old-project: print
ms.assetid: 12970111-3d25-4004-9c6d-8582ef7afef3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IFixedPage, IFixedPage interface [Print Devices], SetPagePart method, IFixedPage::SetPagePart, SetPagePart method [Print Devices], SetPagePart method [Print Devices], IFixedPage interface, SetPagePart,IFixedPage.SetPagePart, filterpipeline/IFixedPage::SetPagePart, filterpipeline_03059a3d-9aac-4ff2-8506-7754327942f6.xml, print.ifixedpage_setpagepart
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
-	IFixedPage.SetPagePart
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IFixedPage::SetPagePart method


## -description


The <b>SetPagePart</b> method associates a new part with the page.


## -syntax


````
HRESULT SetPagePart(
  [in] IUnknown *pUnk
);
````


## -parameters




### -param pUnk [in]

A pointer to the new part.


## -returns



<b>SetPagePart</b> returns an <b>HRESULT</b> value.



