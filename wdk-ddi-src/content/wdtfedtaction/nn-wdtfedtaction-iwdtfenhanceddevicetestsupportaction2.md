---
UID: NN:wdtfedtaction.IWDTFEnhancedDeviceTestSupportAction2
title: IWDTFEnhancedDeviceTestSupportAction2 (wdtfedtaction.h)
description: Defines operations and properties that support the Enhanced Device Test (EDT) filter driver.
old-location: dtf\iwdtfenhanceddevicetestsupportaction2.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFEnhancedDeviceTestSupportAction2 interface"]
ms.keywords: IWDTFEnhancedDeviceTestSupportAction2, IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework], IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFEnhancedDeviceTestSupportAction2, dtf.iwdtfenhanceddevicetestsupportaction2, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2
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
 - IWDTFEnhancedDeviceTestSupportAction2
 - wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFDriverEDTAction.Interop.dll
api_name:
 - IWDTFEnhancedDeviceTestSupportAction2
---

# IWDTFEnhancedDeviceTestSupportAction2 interface


## -description

Defines operations and properties that support the Enhanced Device Test (EDT) filter driver.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFEnhancedDeviceTestSupportAction2</b> interface inherits from <b>IWDTFActionWithCustomActions2</b>. <b>IWDTFEnhancedDeviceTestSupportAction2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -remarks

The EDT filter driver provides support for the 
<a href="/windows-hardware/drivers/ddi/wdtfpnpaction/nn-wdtfpnpaction-iwdtfpnpaction2">IWDTFPNPAction2</a> interface methods 
that are prefixed with <b>EDT</b>.
