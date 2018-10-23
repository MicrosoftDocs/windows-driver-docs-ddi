---
UID: NF:wdtf.IWDTFActions2.Clear
title: IWDTFActions2::Clear
author: windows-driver-content
description: Removes all items from the collection.
old-location: dtf\iwdtfactions2_clear.htm
tech.root: dtf
ms.assetid: f594e1f0-0e7f-4644-a97e-1fce58aa7c71
ms.date: 04/04/2018
ms.keywords: Clear, Clear method [Windows Device Testing Framework], Clear method [Windows Device Testing Framework],IWDTFActions2 interface, IWDTFActions2 interface [Windows Device Testing Framework],Clear method, IWDTFActions2.Clear, IWDTFActions2::Clear, dtf.iwdtfactions2_clear, wdtf/IWDTFActions2::Clear
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFActions2::Clear


## -description


Removes all items from the collection.


## -parameters






## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



The lifetime of <a href="https://msdn.microsoft.com/library/windows/hardware/hh406311">IWDTFAction2</a> interface 
instances are tied to their creator. If you clear all items from a collection, the items are
not destroyed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406331">IWDTFActions2</a>
 

 

