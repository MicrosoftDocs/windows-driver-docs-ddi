---
UID: NF:wdtfdriversetupsystemaction.IWDTFDriverSetupSystemAction2.SnapTriageLogs
title: IWDTFDriverSetupSystemAction2::SnapTriageLogs method
author: windows-driver-content
description: Copies the driver setup triage logs.
old-location: dtf\iwdtfdriversetupsystemaction2_snaptriagelogs.htm
old-project: dtf
ms.assetid: 52f1e529-e1fe-4a08-a0cf-dc08e18d11b5
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: dtf.iwdtfdriversetupsystemaction2_snaptriagelogs, wdtfdriversetupsystemaction/IWDTFDriverSetupSystemAction2::SnapTriageLogs, SnapTriageLogs method [Windows Device Testing Framework], IWDTFDriverSetupSystemAction2 interface, IWDTFDriverSetupSystemAction2 interface [Windows Device Testing Framework], SnapTriageLogs method, Microsoft.WDTF.IWDTFDriverSetupSystemAction2.SnapTriageLogs, IWDTFDriverSetupSystemAction2, SnapTriageLogs method [Windows Device Testing Framework], Microsoft::WDTF::IWDTFDriverSetupSystemAction2::SnapTriageLogs, IWDTFDriverSetupSystemAction2::SnapTriageLogs, SnapTriageLogs
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
req.lib: wdtfdriversetupsystemaction.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFDriverSetupSystemAction.Interop.dll
apiname:
-	IWDTFDriverSetupSystemAction2.SnapTriageLogs
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFDriverSetupSystemAction2::SnapTriageLogs method


## -description


Copies the driver setup triage logs.


## -syntax


````
HRESULT SnapTriageLogs();
````


## -parameters






## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



The <b>SnapTriageLogs</b> method copies the current driver setup 
triage logs to the current directory.




## -see-also

<a href="..\wdtfdriversetupsystemaction\nn-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2.md">IWDTFDriverSetupSystemAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDriverSetupSystemAction2::SnapTriageLogs method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

