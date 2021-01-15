---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportAction2.IsEnabled
title: IWDTFEnhancedDeviceTestSupportAction2::IsEnabled (wdtfedtaction.h)
description: Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled on the target device.
old-location: dtf\iwdtfenhanceddevicetestsupportaction2_isenabled.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFEnhancedDeviceTestSupportAction2::IsEnabled"]
ms.keywords: IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework],IsEnabled method, IWDTFEnhancedDeviceTestSupportAction2.IsEnabled, IWDTFEnhancedDeviceTestSupportAction2::IsEnabled, IsEnabled, IsEnabled method [Windows Device Testing Framework], IsEnabled method [Windows Device Testing Framework],IWDTFEnhancedDeviceTestSupportAction2 interface, Microsoft.WDTF.IWDTFEnhancedDeviceTestSupportAction2.IsEnabled, Microsoft::WDTF::IWDTFEnhancedDeviceTestSupportAction2::IsEnabled, dtf.iwdtfenhanceddevicetestsupportaction2_isenabled, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::IsEnabled
req.header: wdtfedtaction.h
req.include-header: 
req.target-type: Desktop
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
 - IWDTFEnhancedDeviceTestSupportAction2::IsEnabled
 - wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::IsEnabled
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFDriverEDTAction.Interop.dll
api_name:
 - IWDTFEnhancedDeviceTestSupportAction2::IsEnabled
---

# IWDTFEnhancedDeviceTestSupportAction2::IsEnabled


## -description

Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled 
on the target device.

## -parameters

### -param pbEnabled 

[out, retval]
True if the EDT driver is enabled; otherwise, false.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtfedtaction/nn-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2">IWDTFEnhancedDeviceTestSupportAction2</a>

