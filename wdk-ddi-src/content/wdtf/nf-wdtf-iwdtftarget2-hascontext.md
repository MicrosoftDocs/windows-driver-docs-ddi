---
UID: NF:wdtf.IWDTFTarget2.HasContext
title: IWDTFTarget2::HasContext (wdtf.h)
description: Determines whether a given context exists for the target.
old-location: dtf\iwdtftarget2_hascontext.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFTarget2::HasContext"]
ms.keywords: HasContext, HasContext method [Windows Device Testing Framework], HasContext method [Windows Device Testing Framework],IWDTFTarget2 interface, IWDTFTarget2 interface [Windows Device Testing Framework],HasContext method, IWDTFTarget2.HasContext, IWDTFTarget2::HasContext, Microsoft.WDTF.IWDTFTarget2.HasContext, Microsoft::WDTF::IWDTFTarget2::HasContext, dtf.iwdtftarget2_hascontext, wdtf/IWDTFTarget2::HasContext
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
 - IWDTFTarget2::HasContext
 - wdtf/IWDTFTarget2::HasContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTF.Interop.metadata_dll.dll
api_name:
 - IWDTFTarget2::HasContext
---

# IWDTFTarget2::HasContext


## -description

Determines whether a given context exists for the target.

## -parameters

### -param Tag [in]


The context name.

### -param pResult [out, retval]


True if the named context exists; otherwise, false.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a>

