---
UID: NF:wdtf.IWDTFActions2.Remove
title: IWDTFActions2::Remove
author: windows-driver-content
description: Remove an action from the collection.
old-location: dtf\iwdtfactions2_remove.htm
old-project: dtf
ms.assetid: 28cebd7f-1f88-4c3d-8432-c44df4e287d7
ms.author: windowsdriverdev
ms.date: 4/4/2018
ms.keywords: IWDTFActions2 interface [Windows Device Testing Framework],Remove method, IWDTFActions2.Remove, IWDTFActions2::Remove, Remove, Remove method [Windows Device Testing Framework], Remove method [Windows Device Testing Framework],IWDTFActions2 interface, dtf.iwdtfactions2_remove, wdtf/IWDTFActions2::Remove
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
-	IWDTFActions2.Remove
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFActions2::Remove


## -description


Remove an action from the collection.


## -parameters




### -param pAction [in]

The action to remove from this collection.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



The lifetime of <a href="https://msdn.microsoft.com/library/windows/hardware/hh406311">IWDTFAction2</a> interface 
instances are tied to their creator. If you remove an item from a collection, the item is
not destroyed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406331">IWDTFActions2</a>
 

 

