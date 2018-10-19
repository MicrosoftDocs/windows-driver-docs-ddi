---
UID: NF:wdtf.IWDTFTargets2.Remove
title: IWDTFTargets2::Remove
author: windows-driver-content
description: Removes an item from the collection.
old-location: dtf\iwdtftargets2_remove.htm
tech.root: dtf
ms.assetid: 5db8c912-a446-4ae7-a775-f56ffa979283
ms.date: 04/04/2018
ms.keywords: IWDTFTargets2 interface [Windows Device Testing Framework],Remove method, IWDTFTargets2.Remove, IWDTFTargets2::Remove, Microsoft.WDTF.IWDTFTargets2.Remove, Microsoft::WDTF::IWDTFTargets2::Remove, Remove, Remove method [Windows Device Testing Framework], Remove method [Windows Device Testing Framework],IWDTFTargets2 interface, dtf.iwdtftargets2_remove, wdtf/IWDTFTargets2::Remove
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
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
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTFTargets2.Remove
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFTargets2::Remove


## -description


Removes an item from the collection.


## -parameters




### -param pTarget [in]

The item to remove from this collection.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



The lifetime of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a> interface 
instances are tied to their creator. If you remove an item from a collection, the item is
not destroyed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439458">IWDTFTargets2</a>
 

 

