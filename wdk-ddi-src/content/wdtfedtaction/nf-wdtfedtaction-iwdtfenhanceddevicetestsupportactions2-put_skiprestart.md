---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportActions2.put_SkipRestart
title: IWDTFEnhancedDeviceTestSupportActions2::put_SkipRestart method
author: windows-driver-content
description: Sets a value that indicates whether the target device should be restarted by default.
old-location: dtf\iwdtfenhanceddevicetestsupportaction2_skiprestart.htm
tech.root: dtf
ms.assetid: e07c6246-f6f8-4335-9b2c-ae6c2673e188
ms.date: 2/23/2018
ms.keywords: IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework], SkipRestart property, IWDTFEnhancedDeviceTestSupportAction2.SkipRestart, IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart, IWDTFEnhancedDeviceTestSupportActions2, IWDTFEnhancedDeviceTestSupportActions2::put_SkipRestart, Microsoft.WDTF.IWDTFEnhancedDeviceTestSupportAction2.SkipRestart, Microsoft::WDTF::IWDTFEnhancedDeviceTestSupportAction2::SkipRestart, SkipRestart property [Windows Device Testing Framework], SkipRestart property [Windows Device Testing Framework], IWDTFEnhancedDeviceTestSupportAction2 interface, dtf.iwdtfenhanceddevicetestsupportaction2_skiprestart, put_SkipRestart,IWDTFEnhancedDeviceTestSupportActions2.put_SkipRestart, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::SkipRestart, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart
ms.topic: method
req.header: wdtfedtaction.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl: WDTFEDTAction.idl
req.max-support:
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverEDTAction.Interop.dll
req.type-library:
req.lib: wdtfedtaction.h
req.dll:
req.irql:
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFDriverEDTAction.Interop.dll
api_name:
-	IWDTFEnhancedDeviceTestSupportAction2.SkipRestart
-	IWDTFEnhancedDeviceTestSupportAction2.put_SkipRestart
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFEnhancedDeviceTestSupportActions2::put_SkipRestart method


## -description


Sets a value that indicates whether the target device should be restarted by default.

This property is write-only.


## -syntax


```
HRESULT put_SkipRestart(
  [in] VARIANT_BOOL bSkipRestart
);
```


## -parameters


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451004">Enable</a> and
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450971">Disable</a> methods
attempt to restart the target device by default. Use this method to skip that step.




## -see-also

<a href="..\wdtfedtaction\nn-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2.md">IWDTFEnhancedDeviceTestSupportAction2</a>



 

 


