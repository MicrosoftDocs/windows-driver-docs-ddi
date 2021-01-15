---
UID: NF:wdtf.IWDTFTargets2.QuerySingle
title: IWDTFTargets2::QuerySingle (wdtf.h)
description: Returns a single item from the collection.
old-location: dtf\iwdtftargets2_querysingle.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFTargets2::QuerySingle"]
ms.keywords: IWDTFTargets2 interface [Windows Device Testing Framework],QuerySingle method, IWDTFTargets2.QuerySingle, IWDTFTargets2::QuerySingle, Microsoft.WDTF.IWDTFTargets2.QuerySingle, Microsoft::WDTF::IWDTFTargets2::QuerySingle, QuerySingle, QuerySingle method [Windows Device Testing Framework], QuerySingle method [Windows Device Testing Framework],IWDTFTargets2 interface, dtf.iwdtftargets2_querysingle, wdtf/IWDTFTargets2::QuerySingle
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
 - IWDTFTargets2::QuerySingle
 - wdtf/IWDTFTargets2::QuerySingle
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTF.Interop.metadata_dll.dll
api_name:
 - IWDTFTargets2::QuerySingle
---

# IWDTFTargets2::QuerySingle


## -description

Returns a single item from the collection.

## -parameters

### -param SDEL 

[in]
The SDEL query string.

### -param ppTarget 

[out, retval]
The requested item.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftargets2">IWDTFTargets2</a>

