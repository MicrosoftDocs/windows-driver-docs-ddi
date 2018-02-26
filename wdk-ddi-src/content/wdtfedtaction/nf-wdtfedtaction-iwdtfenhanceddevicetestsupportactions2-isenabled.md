---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportActions2.IsEnabled
title: IWDTFEnhancedDeviceTestSupportActions2::IsEnabled method
author: windows-driver-content
description: Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled on the target device.
old-location: dtf\iwdtfenhanceddevicetestsupportactions2_isenabled.htm
old-project: dtf
ms.assetid: 926cf957-3747-4475-a8fc-1c9ca41734f9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 2, :, A, D, E, F, I, IWDTFEnhancedDeviceTestSupportActions2, IWDTFEnhancedDeviceTestSupportActions2 interface [Windows Device Testing Framework], IsEnabled method, IWDTFEnhancedDeviceTestSupportActions2::IsEnabled, IsEnabled method [Windows Device Testing Framework], IsEnabled method [Windows Device Testing Framework], IWDTFEnhancedDeviceTestSupportActions2 interface, IsEnabled,IWDTFEnhancedDeviceTestSupportActions2.IsEnabled, S, T, W, a, b, c, d, dtf.iwdtfenhanceddevicetestsupportactions2_isenabled, e, h, i, l, n, o, p, r, s, t, u, v, wdtfedtaction/IWDTFEnhancedDeviceTestSupportActions2::IsEnabled"
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
req.lib: wdtfedtaction.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wdtfedtaction.h
apiname:
-	IWDTFEnhancedDeviceTestSupportActions2.IsEnabled
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFEnhancedDeviceTestSupportActions2::IsEnabled method


## -description


Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled 
on the target device.


## -syntax


````
HRESULT IsEnabled(
  [out, retval] VARIANT_BOOL *pbEnabled
);
````


## -parameters




### -param pbEnabled [out, retval]

True if the EDT driver is enabled; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfedtaction\nn-wdtfedtaction-iwdtfenhanceddevicetestsupportactions2.md">IWDTFEnhancedDeviceTestSupportActions2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFEnhancedDeviceTestSupportActions2::IsEnabled method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

