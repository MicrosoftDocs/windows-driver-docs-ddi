---
UID: NF:wdtfdriversetupsystemaction.IWDTFDriverSetupSystemAction2.IsImported
title: IWDTFDriverSetupSystemAction2::IsImported method
author: windows-driver-content
description: Returns a value that indicates whether a package has already been imported.
old-location: dtf\iwdtfdriversetupsystemaction2_isimported.htm
old-project: dtf
ms.assetid: 2b6e0fc6-33c6-4dcf-8def-b0e081e2405b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFDriverSetupSystemAction2, IWDTFDriverSetupSystemAction2 interface [Windows Device Testing Framework], IsImported method, IWDTFDriverSetupSystemAction2::IsImported, IsImported method [Windows Device Testing Framework], IsImported method [Windows Device Testing Framework], IWDTFDriverSetupSystemAction2 interface, IsImported,IWDTFDriverSetupSystemAction2.IsImported, Microsoft.WDTF.IWDTFDriverSetupSystemAction2.IsImported, Microsoft::WDTF::IWDTFDriverSetupSystemAction2::IsImported, dtf.iwdtfdriversetupsystemaction2_isimported, wdtfdriversetupsystemaction/IWDTFDriverSetupSystemAction2::IsImported
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfdriversetupsystemaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFDriverSetupSystemAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverSetupSystemAction.Interop.dll
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
-	WDTFDriverSetupSystemAction.Interop.dll
api_name:
-	IWDTFDriverSetupSystemAction2.IsImported
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFDriverSetupSystemAction2::IsImported method


## -description


Returns a value that indicates whether a package has already been imported.


## -parameters




### -param pDp [in]

The package that is to be checked.


### -param bRet






#### - pbIsImported [out, retval]

True if the package has already been imported; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450948">IWDTFDriverSetupSystemAction2</a>
 

 

