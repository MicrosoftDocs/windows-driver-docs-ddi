---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportActions2.IsEnabled
title: IWDTFEnhancedDeviceTestSupportActions2::IsEnabled (wdtfedtaction.h)
description: Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled on the target device.
old-location: dtf\iwdtfenhanceddevicetestsupportactions2_isenabled.htm
tech.root: dtf
ms.assetid: 926cf957-3747-4475-a8fc-1c9ca41734f9
ms.date: 04/04/2018
keywords: ["IWDTFEnhancedDeviceTestSupportActions2::IsEnabled"]
ms.keywords: IWDTFEnhancedDeviceTestSupportActions2 interface [Windows Device Testing Framework],IsEnabled method, IWDTFEnhancedDeviceTestSupportActions2.IsEnabled, IWDTFEnhancedDeviceTestSupportActions2::IsEnabled, IsEnabled, IsEnabled method [Windows Device Testing Framework], IsEnabled method [Windows Device Testing Framework],IWDTFEnhancedDeviceTestSupportActions2 interface, dtf.iwdtfenhanceddevicetestsupportactions2_isenabled, wdtfedtaction/IWDTFEnhancedDeviceTestSupportActions2::IsEnabled
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFEnhancedDeviceTestSupportActions2::IsEnabled
 - wdtfedtaction/IWDTFEnhancedDeviceTestSupportActions2::IsEnabled
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wdtfedtaction.h
api_name:
 - IWDTFEnhancedDeviceTestSupportActions2.IsEnabled
---

# IWDTFEnhancedDeviceTestSupportActions2::IsEnabled


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

<a href="/windows-hardware/drivers/ddi/index">IWDTFEnhancedDeviceTestSupportActions2</a>