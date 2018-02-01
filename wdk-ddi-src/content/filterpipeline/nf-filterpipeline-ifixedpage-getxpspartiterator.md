---
UID: NF:filterpipeline.IFixedPage.GetXpsPartIterator
title: IFixedPage::GetXpsPartIterator method
author: windows-driver-content
description: The GetXpsPartIterator method gets an iterator to enumerate all of the parts that are associated with the page.
old-location: print\ifixedpage_getxpspartiterator.htm
old-project: print
ms.assetid: c4605d9c-b12c-4056-bf19-a67df3ef8c8b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: GetXpsPartIterator method [Print Devices], IFixedPage interface, IFixedPage interface [Print Devices], GetXpsPartIterator method, GetXpsPartIterator method [Print Devices], print.ifixedpage_getxpspartiterator, filterpipeline/IFixedPage::GetXpsPartIterator, IFixedPage, IFixedPage::GetXpsPartIterator, filterpipeline_da8f4ed6-71b0-4d95-867b-7389815fd072.xml, GetXpsPartIterator
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
-	IFixedPage.GetXpsPartIterator
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IFixedPage::GetXpsPartIterator method


## -description


The <b>GetXpsPartIterator</b> method gets an iterator to enumerate all of the parts that are associated with the page. 


## -syntax


````
HRESULT GetXpsPartIterator(
  [out] IXpsPartIterator **pXpsPartIt
);
````


## -parameters




### -param pXpsPartIt [out]

An iterator that you can use to enumerate all of the parts that are associated with the page.


## -returns


<b>GetXpsPartIterator</b> returns an <b>HRESULT</b> value.



## -remarks


Filters should not add or delete parts while using the iterator that the <b>GetXpsPartIterator</b> method retrieves.


