---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportActions2.Disable
title: IWDTFEnhancedDeviceTestSupportActions2::Disable (wdtfedtaction.h)
description: Disables the Enhanced Device Test (EDT) filter driver on the target device.
old-location: dtf\iwdtfenhanceddevicetestsupportactions2_disable.htm
tech.root: dtf
ms.assetid: aaa9604a-1c82-48c5-ab5d-0251bf9f13cd
ms.date: 04/04/2018
ms.keywords: Disable, Disable method [Windows Device Testing Framework], Disable method [Windows Device Testing Framework],IWDTFEnhancedDeviceTestSupportActions2 interface, IWDTFEnhancedDeviceTestSupportActions2 interface [Windows Device Testing Framework],Disable method, IWDTFEnhancedDeviceTestSupportActions2.Disable, IWDTFEnhancedDeviceTestSupportActions2::Disable, dtf.iwdtfenhanceddevicetestsupportactions2_disable, wdtfedtaction/IWDTFEnhancedDeviceTestSupportActions2::Disable
ms.topic: method
f1_keywords:
 - "wdtfedtaction/IWDTFEnhancedDeviceTestSupportActions2.Disable"
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
- IWDTFEnhancedDeviceTestSupportActions2.Disable
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFEnhancedDeviceTestSupportActions2::Disable


## -description


Disables the Enhanced Device Test (EDT) filter driver on the target device.


## -parameters




### -param pbRebootRequired [out, retval]

True if the operation requires a restart to complete; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">IWDTFEnhancedDeviceTestSupportActions2</a>
 

 

