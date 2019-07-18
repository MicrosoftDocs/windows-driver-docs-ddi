---
UID: NF:wdtf.IWDTFTargets2.Clear
title: IWDTFTargets2::Clear (wdtf.h)
description: Removes all items from the collection.
old-location: dtf\iwdtftargets2_clear.htm
tech.root: dtf
ms.assetid: 4fe37240-7cef-4bfb-91be-49a0bca2fa8f
ms.date: 04/04/2018
ms.keywords: Clear, Clear method [Windows Device Testing Framework], Clear method [Windows Device Testing Framework],IWDTFTargets2 interface, IWDTFTargets2 interface [Windows Device Testing Framework],Clear method, IWDTFTargets2.Clear, IWDTFTargets2::Clear, Microsoft.WDTF.IWDTFTargets2.Clear, Microsoft::WDTF::IWDTFTargets2::Clear, dtf.iwdtftargets2_clear, wdtf/IWDTFTargets2::Clear
ms.topic: method
f1_keywords:
 - "wdtf/IWDTFTargets2.Clear"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTF.Interop.metadata_dll.dll
api_name:
- IWDTFTargets2.Clear
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFTargets2::Clear


## -description


Removes all items from the collection.


## -parameters






## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



The lifetime of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a> interface 
instances are tied to their creator. If you clear all items from a collection, the items are
not destroyed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nn-wdtf-iwdtftargets2">IWDTFTargets2</a>
 

 

