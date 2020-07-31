---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.RequestEjectDevice
title: IWDTFPNPActions2::RequestEjectDevice (wdtfpnpaction.h)
description: Initiates a device eject.
old-location: dtf\iwdtfpnpactions2_requestejectdevice.htm
tech.root: dtf
ms.assetid: 6c79b6e7-1134-4de6-b698-e09f295c3e84
ms.date: 04/04/2018
keywords: ["IWDTFPNPActions2::RequestEjectDevice"]
ms.keywords: IWDTFPNPActions2 interface [Windows Device Testing Framework],RequestEjectDevice method, IWDTFPNPActions2.RequestEjectDevice, IWDTFPNPActions2::RequestEjectDevice, RequestEjectDevice, RequestEjectDevice method [Windows Device Testing Framework], RequestEjectDevice method [Windows Device Testing Framework],IWDTFPNPActions2 interface, dtf.iwdtfpnpactions2_requestejectdevice, wdtfpnpaction/IWDTFPNPActions2::RequestEjectDevice
f1_keywords:
 - "wdtfpnpaction/IWDTFPNPActions2.RequestEjectDevice"
 - "IWDTFPNPActions2.RequestEjectDevice"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wdtfpnpaction.h
api_name:
- IWDTFPNPActions2.RequestEjectDevice
targetos: Windows
req.typenames: 
---

# IWDTFPNPActions2::RequestEjectDevice


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">IWDTFPNPActions2</a>
 

 

