---
UID: NF:wdtf.IWDTFTargets2.GetInterfaces
title: IWDTFTargets2::GetInterfaces (wdtf.h)
description: Returns a collection of actions that support the interface - one IWDTFAction2 for each item that has one.
old-location: dtf\iwdtftargets2_getinterfaces.htm
tech.root: dtf
ms.assetid: 8e9735b2-23d3-4fe6-8184-31e7707b6400
ms.date: 04/04/2018
ms.keywords: GetInterfaces, GetInterfaces method [Windows Device Testing Framework], GetInterfaces method [Windows Device Testing Framework],IWDTFTargets2 interface, IWDTFTargets2 interface [Windows Device Testing Framework],GetInterfaces method, IWDTFTargets2.GetInterfaces, IWDTFTargets2::GetInterfaces, Microsoft.WDTF.IWDTFTargets2.GetInterfaces, Microsoft::WDTF::IWDTFTargets2::GetInterfaces, dtf.iwdtftargets2_getinterfaces, wdtf/IWDTFTargets2::GetInterfaces
f1_keywords:
 - "wdtf/IWDTFTargets2.GetInterfaces"
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
- IWDTFTargets2.GetInterfaces
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFTargets2::GetInterfaces


## -description


Returns a collection of actions that support the interface - one <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtfaction2">IWDTFAction2</a> for each item
that has one.


## -parameters




### -param WDTFInterfaceName




### -param MoreTargets [in, optional]

Optional extra arguments that you can use to 
define additional targets to attach to the returned interface. 

This parameter is not 
currently implemented. Set <i>MoreTargets </i>to a <b>VARIANT</b> 
that contains <b>VT_EMPTY</b>.


### -param MonikerSuffix [in, optional]

An optional moniker that defines more options about how 
the interface should be instantiated. 

This parameter is not yet implemented. 
Set <i>MonikerSuffix </i>to a <b>VARIANT</b> that 
contains <b>VT_EMPTY</b>.


### -param ppInterface [out, retval]

The address of a variable that will receive the 
collection of actions.


#### - ProgID [in]

The WDTF ProgID of the requested interface.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



If any items in the collection fail to return an action, this method fails.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftargets2">IWDTFTargets2</a>
 

 

