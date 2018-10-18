---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportAction2.IsRebootRequired
title: IWDTFEnhancedDeviceTestSupportAction2::IsRebootRequired
author: windows-driver-content
description: Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver requires a reboot.
old-location: dtf\iwdtfenhanceddevicetestsupportaction2_isrebootrequired.htm
tech.root: dtf
ms.assetid: 598c4e54-74e1-4e95-bdf9-23bc70f4b530
ms.date: 4/4/2018
ms.keywords: IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework],IsRebootRequired method, IWDTFEnhancedDeviceTestSupportAction2.IsRebootRequired, IWDTFEnhancedDeviceTestSupportAction2::IsRebootRequired, IsRebootRequired, IsRebootRequired method [Windows Device Testing Framework], IsRebootRequired method [Windows Device Testing Framework],IWDTFEnhancedDeviceTestSupportAction2 interface, Microsoft.WDTF.IWDTFEnhancedDeviceTestSupportAction2.IsRebootRequired, Microsoft::WDTF::IWDTFEnhancedDeviceTestSupportAction2::IsRebootRequired, dtf.iwdtfenhanceddevicetestsupportaction2_isrebootrequired, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::IsRebootRequired
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
-	IWDTFEnhancedDeviceTestSupportAction2.IsRebootRequired
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFEnhancedDeviceTestSupportAction2::IsRebootRequired


## -description


Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver requires a reboot.


## -parameters




### -param pbRebootRequired [out, retval]

True if reboot is required; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450969">IWDTFEnhancedDeviceTestSupportAction2</a>
 

 

