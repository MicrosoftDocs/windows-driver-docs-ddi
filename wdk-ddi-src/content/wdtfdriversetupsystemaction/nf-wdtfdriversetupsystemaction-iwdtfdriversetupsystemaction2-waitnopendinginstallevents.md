---
UID: NF:wdtfdriversetupsystemaction.IWDTFDriverSetupSystemAction2.WaitNoPendingInstallEvents
title: IWDTFDriverSetupSystemAction2::WaitNoPendingInstallEvents
author: windows-driver-content
description: Waits until all device installations have completed.
old-location: dtf\iwdtfdriversetupsystemaction2_waitnopendinginstallevents.htm
old-project: dtf
ms.assetid: d58f5d02-d4cf-4208-b5c4-1047b8278ff7
ms.author: windowsdriverdev
ms.date: 4/4/2018
ms.keywords: IWDTFDriverSetupSystemAction2 interface [Windows Device Testing Framework],WaitNoPendingInstallEvents method, IWDTFDriverSetupSystemAction2.WaitNoPendingInstallEvents, IWDTFDriverSetupSystemAction2::WaitNoPendingInstallEvents, Microsoft.WDTF.IWDTFDriverSetupSystemAction2.WaitNoPendingInstallEvents, Microsoft::WDTF::IWDTFDriverSetupSystemAction2::WaitNoPendingInstallEvents, WaitNoPendingInstallEvents, WaitNoPendingInstallEvents method [Windows Device Testing Framework], WaitNoPendingInstallEvents method [Windows Device Testing Framework],IWDTFDriverSetupSystemAction2 interface, dtf.iwdtfdriversetupsystemaction2_waitnopendinginstallevents, wdtfdriversetupsystemaction/IWDTFDriverSetupSystemAction2::WaitNoPendingInstallEvents
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
-	IWDTFDriverSetupSystemAction2.WaitNoPendingInstallEvents
product: Windows
targetos: Windows
req.typenames: 
---

# IWDTFDriverSetupSystemAction2::WaitNoPendingInstallEvents


## -description


Waits until all device installations have completed.


## -parameters




### -param dwTimeout




### -param pNoMoreEvents [out, retval]

True if all device installations completed before the time-out expired; 
otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450948">IWDTFDriverSetupSystemAction2</a>
 

 

