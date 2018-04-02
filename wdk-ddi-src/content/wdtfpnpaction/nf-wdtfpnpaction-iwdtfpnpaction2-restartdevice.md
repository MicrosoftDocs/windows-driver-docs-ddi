---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.RestartDevice
title: IWDTFPNPAction2::RestartDevice method
author: windows-driver-content
description: Initiates a device restart.
old-location: dtf\iwdtfpnpaction2_restartdevice.htm
old-project: dtf
ms.assetid: 6023ca71-47ce-4add-891f-e125252ace08
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFPNPAction2, IWDTFPNPAction2 interface [Windows Device Testing Framework], RestartDevice method, IWDTFPNPAction2::RestartDevice, Microsoft.WDTF.IWDTFPNPAction2.RestartDevice, Microsoft::WDTF::IWDTFPNPAction2::RestartDevice, RestartDevice method [Windows Device Testing Framework], RestartDevice method [Windows Device Testing Framework], IWDTFPNPAction2 interface, RestartDevice,IWDTFPNPAction2.RestartDevice, dtf.iwdtfpnpaction2_restartdevice, wdtfpnpaction/IWDTFPNPAction2::RestartDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfpnpaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFPNPAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverPNPAction.Interop.dll
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
-	WDTFDriverPNPAction.Interop.dll
api_name:
-	IWDTFPNPAction2.RestartDevice
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFPNPAction2::RestartDevice method


## -description


Initiates a device restart.


## -parameters




### -param pbSuccess [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



From a SetupDi interface perspective, this will translate to a DICS_PROPCHANGE.   
See the MSDN docs for details.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451065">IWDTFPNPAction2</a>
 

 

