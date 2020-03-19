---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportActions2.Enable
title: IWDTFEnhancedDeviceTestSupportActions2::Enable (wdtfedtaction.h)
description: Enables the Enhanced Device Test (EDT) filter driver on the target device.
old-location: dtf\iwdtfenhanceddevicetestsupportactions2_enable.htm
tech.root: dtf
ms.assetid: f28d5220-1f02-4984-a4d1-d4c45ea16aa7
ms.date: 04/04/2018
keywords: ["IWDTFEnhancedDeviceTestSupportActions2::Enable"]
ms.keywords: Enable, Enable method [Windows Device Testing Framework], Enable method [Windows Device Testing Framework],IWDTFEnhancedDeviceTestSupportActions2 interface, IWDTFEnhancedDeviceTestSupportActions2 interface [Windows Device Testing Framework],Enable method, IWDTFEnhancedDeviceTestSupportActions2.Enable, IWDTFEnhancedDeviceTestSupportActions2::Enable, dtf.iwdtfenhanceddevicetestsupportactions2_enable, wdtfedtaction/IWDTFEnhancedDeviceTestSupportActions2::Enable
f1_keywords:
 - "wdtfedtaction/IWDTFEnhancedDeviceTestSupportActions2.Enable"
req.header: wdtfedtaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFEDTAction.idl
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
- wdtfedtaction.h
api_name:
- IWDTFEnhancedDeviceTestSupportActions2.Enable
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFEnhancedDeviceTestSupportActions2::Enable


## -description


Enables the Enhanced Device Test (EDT) filter driver on the target device.


## -parameters




### -param pbRebootRequired [out, retval]

True if the operation requires a restart to complete; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">IWDTFEnhancedDeviceTestSupportActions2</a>
 

 

