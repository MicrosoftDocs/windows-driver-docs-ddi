---
UID: NF:wdtf.IWDTFActions2.get__NewEnum
title: IWDTFActions2::get__NewEnum (wdtf.h)
description: Gets a new iteration variable that the For Each loop structure implicitly uses.
old-location: dtf\iwdtfactions2__newenum.htm
tech.root: dtf
ms.assetid: 37f8cccb-2ce3-41aa-b447-024f17ddc262
ms.date: 04/04/2018
keywords: ["IWDTFActions2::get__NewEnum"]
ms.keywords: IWDTFActions2 interface [Windows Device Testing Framework],_NewEnum method, IWDTFActions2.get__NewEnum, IWDTFActions2::_NewEnum, IWDTFActions2::get__NewEnum, _NewEnum method [Windows Device Testing Framework], _NewEnum method [Windows Device Testing Framework],IWDTFActions2 interface, dtf.iwdtfactions2__newenum, get__NewEnum, wdtf/IWDTFActions2::_NewEnum
f1_keywords:
 - "wdtf/IWDTFDeviceDepot2._NewEnum"
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Wdtf.idl
req.max-support: 
req.namespace: 
req.assembly: 
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
- wdtf.h
api_name:
- IWDTFDeviceDepot2._NewEnum
- IWDTFDeviceDepot2.get__NewEnum
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFActions2::get__NewEnum


## -description


Gets a new iteration variable that the <b>For Each</b> 
loop structure implicitly uses.


## -parameters




### -param ppNewEnum [out]

The iteration variable.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



You cannot access the <b>_NewEnum</b> property from the 
JScript programming language.

You must use the Active Template Library (ATL) to implement this functionality. 
For more information about how ATL implements this functionality, see the 
<b>ICollectionOnSTLImpl </b>interface in the MSDN Library.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">IWDTFActions2</a>
 

 


