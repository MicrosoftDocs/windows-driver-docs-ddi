---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.RequestEjectDevice
title: IWDTFPNPAction2::RequestEjectDevice method
author: windows-driver-content
description: Initiates a device eject.
old-location: dtf\iwdtfpnpaction2_requestejectdevice.htm
old-project: dtf
ms.assetid: e4782fd9-0c71-4460-892e-180be41ed3bb
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFPNPAction2, IWDTFPNPAction2 interface [Windows Device Testing Framework], RequestEjectDevice method, IWDTFPNPAction2::RequestEjectDevice, Microsoft.WDTF.IWDTFPNPAction2.RequestEjectDevice, Microsoft::WDTF::IWDTFPNPAction2::RequestEjectDevice, RequestEjectDevice method [Windows Device Testing Framework], RequestEjectDevice method [Windows Device Testing Framework], IWDTFPNPAction2 interface, RequestEjectDevice,IWDTFPNPAction2.RequestEjectDevice, dtf.iwdtfpnpaction2_requestejectdevice, wdtfpnpaction/IWDTFPNPAction2::RequestEjectDevice
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
-	IWDTFPNPAction2.RequestEjectDevice
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFPNPAction2::RequestEjectDevice method


## -description


Initiates a device eject.


## -parameters




### -param pbSuccess [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



This will in essence call <b>CM_Request_Device_Eject()</b>. 
See the MSDN documentation for details.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451065">IWDTFPNPAction2</a>
 

 

