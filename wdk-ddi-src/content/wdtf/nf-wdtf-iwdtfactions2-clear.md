---
UID: NF:wdtf.IWDTFActions2.Clear
title: IWDTFActions2::Clear method
author: windows-driver-content
description: Removes all items from the collection.
old-location: dtf\iwdtfactions2_clear.htm
old-project: dtf
ms.assetid: f594e1f0-0e7f-4644-a97e-1fce58aa7c71
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: Clear method [Windows Device Testing Framework], Clear method [Windows Device Testing Framework], IWDTFActions2 interface, Clear,IWDTFActions2.Clear, IWDTFActions2, IWDTFActions2 interface [Windows Device Testing Framework], Clear method, IWDTFActions2::Clear, dtf.iwdtfactions2_clear, wdtf/IWDTFActions2::Clear
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Wdtf.idl
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
-	wdtf.h
api_name:
-	IWDTFActions2.Clear
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFActions2::Clear method


## -description


Removes all items from the collection.


## -syntax


````
HRESULT Clear();
````


## -parameters






## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



The lifetime of <a href="..\wdtf\nn-wdtf-iwdtfaction2.md">IWDTFAction2</a> interface 
instances are tied to their creator. If you clear all items from a collection, the items are
not destroyed.




## -see-also

<a href="..\wdtf\nn-wdtf-iwdtfactions2.md">IWDTFActions2</a>



 

 


