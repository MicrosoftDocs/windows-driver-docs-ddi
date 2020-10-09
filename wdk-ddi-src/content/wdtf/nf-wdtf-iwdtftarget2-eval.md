---
UID: NF:wdtf.IWDTFTarget2.Eval
title: IWDTFTarget2::Eval (wdtf.h)
description: Evaluate whether this target matches an SDEL statement.
old-location: dtf\iwdtftarget2_eval.htm
tech.root: dtf
ms.assetid: 468cb35d-f816-4233-ba07-8dc47b77d442
ms.date: 04/04/2018
keywords: ["IWDTFTarget2::Eval"]
ms.keywords: Eval, Eval method [Windows Device Testing Framework], Eval method [Windows Device Testing Framework],IWDTFTarget2 interface, IWDTFTarget2 interface [Windows Device Testing Framework],Eval method, IWDTFTarget2.Eval, IWDTFTarget2::Eval, Microsoft.WDTF.IWDTFTarget2.Eval, Microsoft::WDTF::IWDTFTarget2::Eval, dtf.iwdtftarget2_eval, wdtf/IWDTFTarget2::Eval
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFTarget2::Eval
 - wdtf/IWDTFTarget2::Eval
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTF.Interop.metadata_dll.dll
api_name:
 - IWDTFTarget2.Eval
---

# IWDTFTarget2::Eval


## -description

Evaluate whether this target matches an SDEL statement.

## -parameters

### -param SDEL 

[in]
The SDEL statement.

### -param pResult 

[out, retval]
True if the SDEL statement matches this target; 
otherwise, alse.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a>