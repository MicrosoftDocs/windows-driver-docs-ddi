---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportActions2.IsRebootRequired
title: IWDTFEnhancedDeviceTestSupportActions2::IsRebootRequired (wdtfedtaction.h)
description: Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver requires a reboot.
old-location: dtf\iwdtfenhanceddevicetestsupportactions2_isrebootrequired.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFEnhancedDeviceTestSupportActions2::IsRebootRequired"]
ms.keywords: IWDTFEnhancedDeviceTestSupportActions2 interface [Windows Device Testing Framework],IsRebootRequired method, IWDTFEnhancedDeviceTestSupportActions2.IsRebootRequired, IWDTFEnhancedDeviceTestSupportActions2::IsRebootRequired, IsRebootRequired, IsRebootRequired method [Windows Device Testing Framework], IsRebootRequired method [Windows Device Testing Framework],IWDTFEnhancedDeviceTestSupportActions2 interface, dtf.iwdtfenhanceddevicetestsupportactions2_isrebootrequired, wdtfedtaction/IWDTFEnhancedDeviceTestSupportActions2::IsRebootRequired
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
 - IWDTFEnhancedDeviceTestSupportActions2::IsRebootRequired
 - wdtfedtaction/IWDTFEnhancedDeviceTestSupportActions2::IsRebootRequired
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wdtfedtaction.h
api_name:
 - IWDTFEnhancedDeviceTestSupportActions2.IsRebootRequired
---

# IWDTFEnhancedDeviceTestSupportActions2::IsRebootRequired


## -description

Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver requires a reboot.

## -parameters

### -param pbRebootRequired 

[out, retval]
True if reboot is required; otherwise, false.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/index">IWDTFEnhancedDeviceTestSupportActions2</a>
