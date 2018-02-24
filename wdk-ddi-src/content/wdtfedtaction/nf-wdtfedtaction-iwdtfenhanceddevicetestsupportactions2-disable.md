---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportActions2.Disable
title: IWDTFEnhancedDeviceTestSupportActions2::Disable method
author: windows-driver-content
description: Disables the Enhanced Device Test (EDT) filter driver on the target device.
old-location: dtf\iwdtfenhanceddevicetestsupportactions2_disable.htm
old-project: dtf
ms.assetid: aaa9604a-1c82-48c5-ab5d-0251bf9f13cd
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: Disable method [Windows Device Testing Framework], Disable method [Windows Device Testing Framework], IWDTFEnhancedDeviceTestSupportActions2 interface, Disable, IWDTFEnhancedDeviceTestSupportActions2, wdtfedtaction/IWDTFEnhancedDeviceTestSupportActions2::Disable, IWDTFEnhancedDeviceTestSupportActions2 interface [Windows Device Testing Framework], Disable method, dtf.iwdtfenhanceddevicetestsupportactions2_disable, IWDTFEnhancedDeviceTestSupportActions2::Disable
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
-	IWDTFEnhancedDeviceTestSupportActions2.Disable
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFEnhancedDeviceTestSupportActions2::Disable method


## -description


Disables the Enhanced Device Test (EDT) filter driver on the target device.


## -syntax


````
HRESULT Disable(
  [out, retval] VARIANT_BOOL *pbRebootRequired
);
````


## -parameters




### -param pbRebootRequired [out, retval]

True if the operation requires a restart to complete; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfedtaction\nn-wdtfedtaction-iwdtfenhanceddevicetestsupportactions2.md">IWDTFEnhancedDeviceTestSupportActions2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFEnhancedDeviceTestSupportActions2::Disable method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

