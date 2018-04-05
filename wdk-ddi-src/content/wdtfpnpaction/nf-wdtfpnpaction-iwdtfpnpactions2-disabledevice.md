---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.DisableDevice
title: IWDTFPNPActions2::DisableDevice method
author: windows-driver-content
description: Disables the target device.
old-location: dtf\iwdtfpnpactions2_disabledevice.htm
old-project: dtf
ms.assetid: 6aa2c428-d0f7-45e4-b96f-2fbf42cfb32d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DisableDevice method [Windows Device Testing Framework], DisableDevice method [Windows Device Testing Framework], IWDTFPNPActions2 interface, DisableDevice,IWDTFPNPActions2.DisableDevice, IWDTFPNPActions2, IWDTFPNPActions2 interface [Windows Device Testing Framework], DisableDevice method, IWDTFPNPActions2::DisableDevice, dtf.iwdtfpnpactions2_disabledevice, wdtfpnpaction/IWDTFPNPActions2::DisableDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfpnpaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFPNPAction.idl
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
-	wdtfpnpaction.h
api_name:
-	IWDTFPNPActions2.DisableDevice
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFPNPActions2::DisableDevice method


## -description


Disables the target device.


## -parameters




### -param pbRebootRequired [out, retval]

True if the operation requires a restart to complete; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451094">IWDTFPNPActions2</a>
 

 

