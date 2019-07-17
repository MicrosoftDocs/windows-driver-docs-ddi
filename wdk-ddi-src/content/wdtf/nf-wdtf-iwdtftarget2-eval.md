---
UID: NF:wdtf.IWDTFTarget2.Eval
title: IWDTFTarget2::Eval (wdtf.h)
description: Evaluate whether this target matches an SDEL statement.
old-location: dtf\iwdtftarget2_eval.htm
tech.root: dtf
ms.assetid: 468cb35d-f816-4233-ba07-8dc47b77d442
ms.date: 04/04/2018
ms.keywords: Eval, Eval method [Windows Device Testing Framework], Eval method [Windows Device Testing Framework],IWDTFTarget2 interface, IWDTFTarget2 interface [Windows Device Testing Framework],Eval method, IWDTFTarget2.Eval, IWDTFTarget2::Eval, Microsoft.WDTF.IWDTFTarget2.Eval, Microsoft::WDTF::IWDTFTarget2::Eval, dtf.iwdtftarget2_eval, wdtf/IWDTFTarget2::Eval
ms.topic: method
f1_keywords:
 - "wdtf/IWDTFTarget2.Eval"
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
- IWDTFTarget2.Eval
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFTarget2::Eval


## -description


Evaluate whether this target matches an SDEL statement.


## -parameters




### -param SDEL [in]

The SDEL statement.


### -param pResult [out, retval]

True if the SDEL statement matches this target; 
otherwise, alse.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a>
 

 

