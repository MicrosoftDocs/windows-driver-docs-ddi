---
UID: NF:wdtfdriversetupdeviceaction.IWDTFDriverSetupAction2.UnInstallDriverPermanently
title: IWDTFDriverSetupAction2::UnInstallDriverPermanently method
author: windows-driver-content
description: Uninstalls the current driver for the target device.
old-location: dtf\iwdtfdriversetupaction2_uninstalldriverpermanently.htm
old-project: dtf
ms.assetid: 60346c38-0ee2-4f69-8fef-0a47a6375430
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: UnInstallDriverPermanently method [Windows Device Testing Framework], IWDTFDriverSetupAction2 interface, dtf.iwdtfdriversetupaction2_uninstalldriverpermanently, Microsoft.WDTF.IWDTFDriverSetupAction2.UnInstallDriverPermanently, Microsoft::WDTF::IWDTFDriverSetupAction2::UnInstallDriverPermanently, UnInstallDriverPermanently method [Windows Device Testing Framework], wdtfdriversetupdeviceaction/IWDTFDriverSetupAction2::UnInstallDriverPermanently, IWDTFDriverSetupAction2::UnInstallDriverPermanently, IWDTFDriverSetupAction2 interface [Windows Device Testing Framework], UnInstallDriverPermanently method, UnInstallDriverPermanently, IWDTFDriverSetupAction2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfdriversetupdeviceaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFDriverSetupDeviceAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverSetupDeviceAction.Interop.dll
req.type-library: 
req.lib: wdtfdriversetupdeviceaction.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFDriverSetupDeviceAction.Interop.dll
apiname:
-	IWDTFDriverSetupAction2.UnInstallDriverPermanently
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFDriverSetupAction2::UnInstallDriverPermanently method


## -description


Uninstalls the current driver for the target device.


## -syntax


````
HRESULT UnInstallDriverPermanently();
````


## -parameters




### -param pbReboot






## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfdriversetupdeviceaction\nn-wdtfdriversetupdeviceaction-iwdtfdriversetupaction2.md">IWDTFDriverSetupAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDriverSetupAction2::UnInstallDriverPermanently method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

