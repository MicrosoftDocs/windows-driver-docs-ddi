---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.RemoveDevice
title: IWDTFPNPActions2::RemoveDevice (wdtfpnpaction.h)
description: Removes the device.
old-location: dtf\iwdtfpnpactions2_removedevice.htm
tech.root: dtf
ms.assetid: 8926e96e-b738-47ff-a5c4-8bc15943c6a4
ms.date: 04/04/2018
keywords: ["IWDTFPNPActions2::RemoveDevice"]
ms.keywords: IWDTFPNPActions2 interface [Windows Device Testing Framework],RemoveDevice method, IWDTFPNPActions2.RemoveDevice, IWDTFPNPActions2::RemoveDevice, RemoveDevice, RemoveDevice method [Windows Device Testing Framework], RemoveDevice method [Windows Device Testing Framework],IWDTFPNPActions2 interface, dtf.iwdtfpnpactions2_removedevice, wdtfpnpaction/IWDTFPNPActions2::RemoveDevice
f1_keywords:
 - "wdtfpnpaction/IWDTFPNPActions2.RemoveDevice"
 - "IWDTFPNPActions2.RemoveDevice"
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
- IWDTFPNPActions2.RemoveDevice
targetos: Windows
req.typenames: 
---

# IWDTFPNPActions2::RemoveDevice


## -description


Removes the device.


## -parameters




### -param pbSuccess 
[out, retval]
True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



Under the covers, this will call DIF_REMOVE.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">IWDTFPNPActions2</a>
 

 

