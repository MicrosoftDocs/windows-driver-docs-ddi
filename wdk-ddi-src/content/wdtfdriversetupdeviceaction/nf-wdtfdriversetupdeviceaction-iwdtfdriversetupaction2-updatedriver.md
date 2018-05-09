---
UID: NF:wdtfdriversetupdeviceaction.IWDTFDriverSetupAction2.UpdateDriver
title: IWDTFDriverSetupAction2::UpdateDriver
author: windows-driver-content
description: Updates the target device with a driver from the driver package.
old-location: dtf\iwdtfdriversetupaction2_updatedriver.htm
old-project: dtf
ms.assetid: 4eb49aae-a7de-4038-9d57-003bb30d7ea8
ms.author: windowsdriverdev
ms.date: 4/4/2018
ms.keywords: IWDTFDriverSetupAction2 interface [Windows Device Testing Framework],UpdateDriver method, IWDTFDriverSetupAction2.UpdateDriver, IWDTFDriverSetupAction2::UpdateDriver, Microsoft.WDTF.IWDTFDriverSetupAction2.UpdateDriver, Microsoft::WDTF::IWDTFDriverSetupAction2::UpdateDriver, UpdateDriver, UpdateDriver method [Windows Device Testing Framework], UpdateDriver method [Windows Device Testing Framework],IWDTFDriverSetupAction2 interface, dtf.iwdtfdriversetupaction2_updatedriver, wdtfdriversetupdeviceaction/IWDTFDriverSetupAction2::UpdateDriver
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFDriverSetupDeviceAction.Interop.dll
api_name:
-	IWDTFDriverSetupAction2.UpdateDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFDriverSetupAction2::UpdateDriver


## -description


Updates the target device with a driver from the driver package.


## -parameters




### -param pDp [in]

The driver package.


### -param pbReboot






#### - pbRebootRequired [out, retval]

True if the device must reboot after the update; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450938">IWDTFDriverSetupAction2</a>
 

 

