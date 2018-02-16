---
UID: NF:wdtfdriversetupdeviceaction.IWDTFDriverSetupAction2.UpdateDriver
title: IWDTFDriverSetupAction2::UpdateDriver method
author: windows-driver-content
description: Updates the target device with a driver from the driver package.
old-location: dtf\iwdtfdriversetupaction2_updatedriver.htm
old-project: dtf
ms.assetid: 4eb49aae-a7de-4038-9d57-003bb30d7ea8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: UpdateDriver method [Windows Device Testing Framework], Microsoft.WDTF.IWDTFDriverSetupAction2.UpdateDriver, IWDTFDriverSetupAction2::UpdateDriver, dtf.iwdtfdriversetupaction2_updatedriver, UpdateDriver, IWDTFDriverSetupAction2, IWDTFDriverSetupAction2 interface [Windows Device Testing Framework], UpdateDriver method, Microsoft::WDTF::IWDTFDriverSetupAction2::UpdateDriver, wdtfdriversetupdeviceaction/IWDTFDriverSetupAction2::UpdateDriver, UpdateDriver method [Windows Device Testing Framework], IWDTFDriverSetupAction2 interface
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
-	IWDTFDriverSetupAction2.UpdateDriver
product: Windows
targetos: Windows
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
req.product: Windows 10 or later.
---

# IWDTFDriverSetupAction2::UpdateDriver method


## -description


Updates the target device with a driver from the driver package.


## -syntax


````
HRESULT UpdateDriver(
  [in]          IWDTFDriverPackageAction2 *pDp,
  [out, retval] VARIANT_BOOL              *pbRebootRequired
);
````


## -parameters




### -param pDp [in]

The driver package.


### -param pbReboot






#### - pbRebootRequired [out, retval]

True if the device must reboot after the update; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfdriversetupdeviceaction\nn-wdtfdriversetupdeviceaction-iwdtfdriversetupaction2.md">IWDTFDriverSetupAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDriverSetupAction2::UpdateDriver method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

