---
UID: NF:filterpipeline.IFixedPage.GetXpsPartIterator
title: IFixedPage::GetXpsPartIterator (filterpipeline.h)
description: The GetXpsPartIterator method gets an iterator to enumerate all of the parts that are associated with the page.
old-location: print\ifixedpage_getxpspartiterator.htm
tech.root: print
ms.assetid: c4605d9c-b12c-4056-bf19-a67df3ef8c8b
ms.date: 04/20/2018
ms.keywords: GetXpsPartIterator, GetXpsPartIterator method [Print Devices], GetXpsPartIterator method [Print Devices],IFixedPage interface, IFixedPage interface [Print Devices],GetXpsPartIterator method, IFixedPage.GetXpsPartIterator, IFixedPage::GetXpsPartIterator, filterpipeline/IFixedPage::GetXpsPartIterator, filterpipeline_da8f4ed6-71b0-4d95-867b-7389815fd072.xml, print.ifixedpage_getxpspartiterator
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- filterpipeline.h
api_name:
- IFixedPage.GetXpsPartIterator
product:
- Windows
targetos: Windows
req.typenames: 
---

# IFixedPage::GetXpsPartIterator


## -description


The <b>GetXpsPartIterator</b> method gets an iterator to enumerate all of the parts that are associated with the page. 


## -parameters




### -param pXpsPartIt [out]

An iterator that you can use to enumerate all of the parts that are associated with the page.


## -returns



<b>GetXpsPartIterator</b> returns an <b>HRESULT</b> value.




## -remarks



Filters should not add or delete parts while using the iterator that the <b>GetXpsPartIterator</b> method retrieves.



