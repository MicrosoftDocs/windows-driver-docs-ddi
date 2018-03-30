---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportActions2.IsRebootRequired
title: IWDTFEnhancedDeviceTestSupportActions2::IsRebootRequired method
author: windows-driver-content
description: Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver requires a reboot.
old-location: dtf\iwdtfenhanceddevicetestsupportactions2_isrebootrequired.htm
old-project: dtf
ms.assetid: 76d4f209-e38d-4ab3-94bf-3cc7fdff950c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFEnhancedDeviceTestSupportActions2, IWDTFEnhancedDeviceTestSupportActions2 interface [Windows Device Testing Framework], IsRebootRequired method, IWDTFEnhancedDeviceTestSupportActions2::IsRebootRequired, IsRebootRequired method [Windows Device Testing Framework], IsRebootRequired method [Windows Device Testing Framework], IWDTFEnhancedDeviceTestSupportActions2 interface, IsRebootRequired,IWDTFEnhancedDeviceTestSupportActions2.IsRebootRequired, dtf.iwdtfenhanceddevicetestsupportactions2_isrebootrequired, wdtfedtaction/IWDTFEnhancedDeviceTestSupportActions2::IsRebootRequired
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	wdtfedtaction.h
api_name:
-	IWDTFEnhancedDeviceTestSupportActions2.IsRebootRequired
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFEnhancedDeviceTestSupportActions2::IsRebootRequired method


## -description


Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver requires a reboot.


## -parameters




### -param pbRebootRequired [out, retval]

True if reboot is required; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450998">IWDTFEnhancedDeviceTestSupportActions2</a>
 

 

