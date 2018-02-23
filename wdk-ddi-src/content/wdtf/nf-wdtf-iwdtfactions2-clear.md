---
UID: NF:wdtf.IWDTFActions2.Clear
title: IWDTFActions2::Clear method
author: windows-driver-content
description: Removes all items from the collection.
old-location: dtf\iwdtfactions2_clear.htm
old-project: dtf
ms.assetid: f594e1f0-0e7f-4644-a97e-1fce58aa7c71
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdtf/IWDTFActions2::Clear, Clear, IWDTFActions2 interface [Windows Device Testing Framework], Clear method, IWDTFActions2::Clear, dtf.iwdtfactions2_clear, Clear method [Windows Device Testing Framework], IWDTFActions2 interface, Clear method [Windows Device Testing Framework], IWDTFActions2
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
req.lib: wdtf.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wdtf.h
apiname:
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFActions2::Clear method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

