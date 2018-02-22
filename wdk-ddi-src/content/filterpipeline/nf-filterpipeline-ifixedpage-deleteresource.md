---
UID: NF:filterpipeline.IFixedPage.DeleteResource
title: IFixedPage::DeleteResource method
author: windows-driver-content
description: The DeleteResource method deletes a resource that is associated with the page.
old-location: print\ifixedpage_deleteresource.htm
old-project: print
ms.assetid: 11aefa65-9f1c-4a6e-aac0-8727c6e00a02
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: IFixedPage::DeleteResource, IFixedPage, DeleteResource method [Print Devices], filterpipeline/IFixedPage::DeleteResource, DeleteResource method [Print Devices], IFixedPage interface, DeleteResource, IFixedPage interface [Print Devices], DeleteResource method, filterpipeline_b87a40f2-68cc-4664-9531-aaffc41b1a1a.xml, print.ifixedpage_deleteresource
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
-	IFixedPage.DeleteResource
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IFixedPage::DeleteResource method


## -description


The <b>DeleteResource</b> method deletes a resource that is associated with the page.


## -syntax


````
HRESULT DeleteResource(
  [in] const wchar_t *uri
);
````


## -parameters




### -param uri [in]

The URI to the resource that should be unassociated from the page.


## -returns



<b>DeleteResource</b> returns an <b>HRESULT</b> value.



