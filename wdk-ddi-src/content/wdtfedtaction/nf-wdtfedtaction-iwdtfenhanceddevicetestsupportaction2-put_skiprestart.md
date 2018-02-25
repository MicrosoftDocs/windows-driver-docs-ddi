---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportAction2.put_SkipRestart
title: IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart method
author: windows-driver-content
description: Sets a value that indicates whether the target device should be restarted by default.
old-location: dtf\iwdtfenhanceddevicetestsupportaction2_skiprestart.htm
old-project: dtf
ms.assetid: e07c6246-f6f8-4335-9b2c-ae6c2673e188
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., 2, :, A, D, E, F, I, IWDTFEnhancedDeviceTestSupportAction2, IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework], SkipRestart property, IWDTFEnhancedDeviceTestSupportAction2.SkipRestart, IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart, Microsoft.WDTF.IWDTFEnhancedDeviceTestSupportAction2.SkipRestart, Microsoft::WDTF::IWDTFEnhancedDeviceTestSupportAction2::SkipRestart, R, S, SkipRestart property [Windows Device Testing Framework], SkipRestart property [Windows Device Testing Framework], IWDTFEnhancedDeviceTestSupportAction2 interface, T, W, _, a, c, d, dtf.iwdtfenhanceddevicetestsupportaction2_skiprestart, e, h, i, k, n, o, p, put_SkipRestart,IWDTFEnhancedDeviceTestSupportAction2.put_SkipRestart, r, s, t, u, v, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::SkipRestart, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFDriverEDTAction.Interop.dll
apiname:
-	IWDTFEnhancedDeviceTestSupportAction2.SkipRestart
-	IWDTFEnhancedDeviceTestSupportAction2.put_SkipRestart
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart method


## -description


Sets a value that indicates whether the target device should be restarted by default.

This property is write-only.


## -syntax


````
HRESULT put_SkipRestart(
  [in] VARIANT_BOOL bSkipRestart
);
````


## -parameters


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451004">Enable</a> and 
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450971">Disable</a> methods 
attempt to restart the target device by default. Use this method to skip that step.




## -see-also

<a href="..\wdtfedtaction\nn-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2.md">IWDTFEnhancedDeviceTestSupportAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFEnhancedDeviceTestSupportAction2::SkipRestart property%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

