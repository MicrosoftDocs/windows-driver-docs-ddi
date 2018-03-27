---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportAction2.IsEnabled
title: IWDTFEnhancedDeviceTestSupportAction2::IsEnabled method
author: windows-driver-content
description: Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled on the target device.
old-location: dtf\iwdtfenhanceddevicetestsupportaction2_isenabled.htm
old-project: dtf
ms.assetid: 7d75d8e7-1416-4075-bc75-b4d2cd4f65a5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFEnhancedDeviceTestSupportAction2, IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework], IsEnabled method, IWDTFEnhancedDeviceTestSupportAction2::IsEnabled, IsEnabled method [Windows Device Testing Framework], IsEnabled method [Windows Device Testing Framework], IWDTFEnhancedDeviceTestSupportAction2 interface, IsEnabled,IWDTFEnhancedDeviceTestSupportAction2.IsEnabled, Microsoft.WDTF.IWDTFEnhancedDeviceTestSupportAction2.IsEnabled, Microsoft::WDTF::IWDTFEnhancedDeviceTestSupportAction2::IsEnabled, dtf.iwdtfenhanceddevicetestsupportaction2_isenabled, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::IsEnabled
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFDriverEDTAction.Interop.dll
api_name:
-	IWDTFEnhancedDeviceTestSupportAction2.IsEnabled
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFEnhancedDeviceTestSupportAction2::IsEnabled method


## -description


Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled 
on the target device.


## -parameters




### -param pbEnabled [out, retval]

True if the EDT driver is enabled; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450969">IWDTFEnhancedDeviceTestSupportAction2</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFEnhancedDeviceTestSupportAction2::IsEnabled method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

