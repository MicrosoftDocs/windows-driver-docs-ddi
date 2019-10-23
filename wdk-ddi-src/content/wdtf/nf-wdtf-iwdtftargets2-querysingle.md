---
UID: NF:wdtf.IWDTFTargets2.QuerySingle
title: IWDTFTargets2::QuerySingle (wdtf.h)
description: Returns a single item from the collection.
old-location: dtf\iwdtftargets2_querysingle.htm
tech.root: dtf
ms.assetid: d9aa36b6-8ce4-41dd-96a8-104fa9094405
ms.date: 04/04/2018
ms.keywords: IWDTFTargets2 interface [Windows Device Testing Framework],QuerySingle method, IWDTFTargets2.QuerySingle, IWDTFTargets2::QuerySingle, Microsoft.WDTF.IWDTFTargets2.QuerySingle, Microsoft::WDTF::IWDTFTargets2::QuerySingle, QuerySingle, QuerySingle method [Windows Device Testing Framework], QuerySingle method [Windows Device Testing Framework],IWDTFTargets2 interface, dtf.iwdtftargets2_querysingle, wdtf/IWDTFTargets2::QuerySingle
ms.topic: method
f1_keywords:
 - "wdtf/IWDTFTargets2.QuerySingle"
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
- IWDTFTargets2.QuerySingle
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFTargets2::QuerySingle


## -description


Returns a single item from the collection.


## -parameters




### -param SDEL [in]

The SDEL query string.


### -param ppTarget [out, retval]

The requested item.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftargets2">IWDTFTargets2</a>
 

 

