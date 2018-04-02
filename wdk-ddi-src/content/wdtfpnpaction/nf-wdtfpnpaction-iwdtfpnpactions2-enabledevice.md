---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.EnableDevice
title: IWDTFPNPActions2::EnableDevice method
author: windows-driver-content
description: Enables the target device.
old-location: dtf\iwdtfpnpactions2_enabledevice.htm
old-project: dtf
ms.assetid: a215710d-c2ea-4bbb-9eab-c808501bf8d8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EnableDevice method [Windows Device Testing Framework], EnableDevice method [Windows Device Testing Framework], IWDTFPNPActions2 interface, EnableDevice,IWDTFPNPActions2.EnableDevice, IWDTFPNPActions2, IWDTFPNPActions2 interface [Windows Device Testing Framework], EnableDevice method, IWDTFPNPActions2::EnableDevice, dtf.iwdtfpnpactions2_enabledevice, wdtfpnpaction/IWDTFPNPActions2::EnableDevice
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
-	IWDTFPNPActions2.EnableDevice
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFPNPActions2::EnableDevice method


## -description


Enables the target device.


## -parameters




### -param pbRebootRequired [out, retval]

True if the operation requires a restart to complete; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451094">IWDTFPNPActions2</a>
 

 

