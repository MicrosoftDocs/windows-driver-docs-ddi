---
UID: NF:wdtf.IWDTFTargets2.Clear
title: IWDTFTargets2::Clear method
author: windows-driver-content
description: Removes all items from the collection.
old-location: dtf\iwdtftargets2_clear.htm
old-project: dtf
ms.assetid: 4fe37240-7cef-4bfb-91be-49a0bca2fa8f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: Clear method [Windows Device Testing Framework], Clear method [Windows Device Testing Framework], IWDTFTargets2 interface, Clear,IWDTFTargets2.Clear, IWDTFTargets2, IWDTFTargets2 interface [Windows Device Testing Framework], Clear method, IWDTFTargets2::Clear, Microsoft.WDTF.IWDTFTargets2.Clear, Microsoft::WDTF::IWDTFTargets2::Clear, dtf.iwdtftargets2_clear, wdtf/IWDTFTargets2::Clear
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IWDTFTargets2.Clear
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFTargets2::Clear method


## -description


Removes all items from the collection.


## -parameters






## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



The lifetime of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a> interface 
instances are tied to their creator. If you clear all items from a collection, the items are
not destroyed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439458">IWDTFTargets2</a>
 

 

