---
UID: NF:wdtf.IWDTFTargets2.Eval
title: IWDTFTargets2::Eval (wdtf.h)
description: Evaluates whether all items in the collection match an SDEL statement.
old-location: dtf\iwdtftargets2_eval.htm
tech.root: dtf
ms.assetid: 028a1fa9-686d-4f56-a49f-a7e90f960018
ms.date: 04/04/2018
ms.keywords: Eval, Eval method [Windows Device Testing Framework], Eval method [Windows Device Testing Framework],IWDTFTargets2 interface, IWDTFTargets2 interface [Windows Device Testing Framework],Eval method, IWDTFTargets2.Eval, IWDTFTargets2::Eval, Microsoft.WDTF.IWDTFTargets2.Eval, Microsoft::WDTF::IWDTFTargets2::Eval, dtf.iwdtftargets2_eval, wdtf/IWDTFTargets2::Eval
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTF.Interop.metadata_dll.dll
api_name:
- IWDTFTargets2.Eval
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFTargets2::Eval


## -description


Evaluates whether all items in the collection match an SDEL statement.


## -parameters




### -param SDEL [in]

The SDEL query string.


### -param pResult [out, retval]

True if all items match; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nn-wdtf-iwdtftargets2">IWDTFTargets2</a>
 

 

