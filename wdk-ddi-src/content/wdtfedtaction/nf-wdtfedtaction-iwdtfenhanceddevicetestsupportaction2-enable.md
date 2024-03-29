---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportAction2.Enable
title: IWDTFEnhancedDeviceTestSupportAction2::Enable (wdtfedtaction.h)
description: Enables the Enhanced Device Test (EDT) filter driver on the target device.
old-location: dtf\iwdtfenhanceddevicetestsupportaction2_enable.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFEnhancedDeviceTestSupportAction2::Enable"]
ms.keywords: Enable, Enable method [Windows Device Testing Framework], Enable method [Windows Device Testing Framework],IWDTFEnhancedDeviceTestSupportAction2 interface, IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework],Enable method, IWDTFEnhancedDeviceTestSupportAction2.Enable, IWDTFEnhancedDeviceTestSupportAction2::Enable, Microsoft.WDTF.IWDTFEnhancedDeviceTestSupportAction2.Enable, Microsoft::WDTF::IWDTFEnhancedDeviceTestSupportAction2::Enable, dtf.iwdtfenhanceddevicetestsupportaction2_enable, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::Enable
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
 - IWDTFEnhancedDeviceTestSupportAction2::Enable
 - wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::Enable
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFDriverEDTAction.Interop.dll
api_name:
 - IWDTFEnhancedDeviceTestSupportAction2::Enable
---

# IWDTFEnhancedDeviceTestSupportAction2::Enable


## -description

Enables the Enhanced Device Test (EDT) filter driver on the target device.

## -parameters

### -param pbRebootRequired [out, retval]


True if the operation requires a restart to complete; otherwise, false.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtfedtaction/nn-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2">IWDTFEnhancedDeviceTestSupportAction2</a>

