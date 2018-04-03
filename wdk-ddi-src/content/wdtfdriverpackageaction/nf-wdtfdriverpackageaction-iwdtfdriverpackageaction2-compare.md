---
UID: NF:wdtfdriverpackageaction.IWDTFDriverPackageAction2.Compare
title: IWDTFDriverPackageAction2::Compare method
author: windows-driver-content
description: Compares two driver packages.
old-location: dtf\iwdtfdriverpackageaction2_compare.htm
old-project: dtf
ms.assetid: fa93d535-fe26-40cc-b08a-88841dcfdc96
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: Compare method [Windows Device Testing Framework], Compare method [Windows Device Testing Framework], IWDTFDriverPackageAction2 interface, Compare,IWDTFDriverPackageAction2.Compare, IWDTFDriverPackageAction2, IWDTFDriverPackageAction2 interface [Windows Device Testing Framework], Compare method, IWDTFDriverPackageAction2::Compare, Microsoft.WDTF.IWDTFDriverPackageAction2.Compare, Microsoft::WDTF::IWDTFDriverPackageAction2::Compare, dtf.iwdtfdriverpackageaction2_compare, wdtfdriverpackageaction/IWDTFDriverPackageAction2::Compare
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfdriverpackageaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFDriverPackageAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverPackageAction.Interop.dll
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
-	WDTFDriverPackageAction.Interop.dll
api_name:
-	IWDTFDriverPackageAction2.Compare
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFDriverPackageAction2::Compare method


## -description


Compares two driver packages.


## -parameters




### -param pDp [in]

The second driver package.


### -param pbIsIdentical [out, retval]

True if the two driver packages are the same; 
otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406427">IWDTFDriverPackageAction2</a>
 

 

