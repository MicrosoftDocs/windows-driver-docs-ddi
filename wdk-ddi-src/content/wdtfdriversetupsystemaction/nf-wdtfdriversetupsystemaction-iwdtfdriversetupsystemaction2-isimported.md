---
UID: NF:wdtfdriversetupsystemaction.IWDTFDriverSetupSystemAction2.IsImported
title: IWDTFDriverSetupSystemAction2::IsImported (wdtfdriversetupsystemaction.h)
description: Returns a value that indicates whether a package has already been imported.
old-location: dtf\iwdtfdriversetupsystemaction2_isimported.htm
tech.root: dtf
ms.assetid: 2b6e0fc6-33c6-4dcf-8def-b0e081e2405b
ms.date: 04/04/2018
ms.keywords: IWDTFDriverSetupSystemAction2 interface [Windows Device Testing Framework],IsImported method, IWDTFDriverSetupSystemAction2.IsImported, IWDTFDriverSetupSystemAction2::IsImported, IsImported, IsImported method [Windows Device Testing Framework], IsImported method [Windows Device Testing Framework],IWDTFDriverSetupSystemAction2 interface, Microsoft.WDTF.IWDTFDriverSetupSystemAction2.IsImported, Microsoft::WDTF::IWDTFDriverSetupSystemAction2::IsImported, dtf.iwdtfdriversetupsystemaction2_isimported, wdtfdriversetupsystemaction/IWDTFDriverSetupSystemAction2::IsImported
ms.topic: method
f1_keywords:
 - "wdtfdriversetupsystemaction/IWDTFDriverSetupSystemAction2.IsImported"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTFDriverSetupSystemAction.Interop.dll
api_name:
- IWDTFDriverSetupSystemAction2.IsImported
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFDriverSetupSystemAction2::IsImported


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfdriversetupsystemaction/nn-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2">IWDTFDriverSetupSystemAction2</a>
 

 

