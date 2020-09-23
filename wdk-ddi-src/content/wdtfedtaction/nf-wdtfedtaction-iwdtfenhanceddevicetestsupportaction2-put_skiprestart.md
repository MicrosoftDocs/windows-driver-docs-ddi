---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportAction2.put_SkipRestart
title: IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart (wdtfedtaction.h)
description: Sets a value that indicates whether the target device should be restarted by default.
old-location: dtf\iwdtfenhanceddevicetestsupportaction2_skiprestart.htm
tech.root: dtf
ms.assetid: e07c6246-f6f8-4335-9b2c-ae6c2673e188
ms.date: 04/04/2018
keywords: ["IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart"]
ms.keywords: IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework],SkipRestart property, IWDTFEnhancedDeviceTestSupportAction2.SkipRestart, IWDTFEnhancedDeviceTestSupportAction2.put_SkipRestart, IWDTFEnhancedDeviceTestSupportAction2::SkipRestart, IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart, Microsoft.WDTF.IWDTFEnhancedDeviceTestSupportAction2.SkipRestart, Microsoft::WDTF::IWDTFEnhancedDeviceTestSupportAction2::SkipRestart, SkipRestart property [Windows Device Testing Framework], SkipRestart property [Windows Device Testing Framework],IWDTFEnhancedDeviceTestSupportAction2 interface, dtf.iwdtfenhanceddevicetestsupportaction2_skiprestart, put_SkipRestart, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::SkipRestart, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart
 - wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFDriverEDTAction.Interop.dll
api_name:
 - IWDTFEnhancedDeviceTestSupportAction2.SkipRestart
 - IWDTFEnhancedDeviceTestSupportAction2.put_SkipRestart
---

# IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart


## -description

Sets a value that indicates whether the target device should be restarted by default.

This property is write-only.

## -parameters

## -remarks

The <a href="/windows-hardware/drivers/ddi/index">Enable</a> and 
<a href="/windows-hardware/drivers/ddi/wdtfedtaction/nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-disable">Disable</a> methods 
attempt to restart the target device by default. Use this method to skip that step.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtfedtaction/nn-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2">IWDTFEnhancedDeviceTestSupportAction2</a>