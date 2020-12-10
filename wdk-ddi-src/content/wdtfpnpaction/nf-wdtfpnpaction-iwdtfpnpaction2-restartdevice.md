---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.RestartDevice
title: IWDTFPNPAction2::RestartDevice (wdtfpnpaction.h)
description: Initiates a device restart.
old-location: dtf\iwdtfpnpaction2_restartdevice.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFPNPAction2::RestartDevice"]
ms.keywords: IWDTFPNPAction2 interface [Windows Device Testing Framework],RestartDevice method, IWDTFPNPAction2.RestartDevice, IWDTFPNPAction2::RestartDevice, Microsoft.WDTF.IWDTFPNPAction2.RestartDevice, Microsoft::WDTF::IWDTFPNPAction2::RestartDevice, RestartDevice, RestartDevice method [Windows Device Testing Framework], RestartDevice method [Windows Device Testing Framework],IWDTFPNPAction2 interface, dtf.iwdtfpnpaction2_restartdevice, wdtfpnpaction/IWDTFPNPAction2::RestartDevice
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFPNPAction2::RestartDevice
 - wdtfpnpaction/IWDTFPNPAction2::RestartDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFDriverPNPAction.Interop.dll
api_name:
 - IWDTFPNPAction2.RestartDevice
---

# IWDTFPNPAction2::RestartDevice


## -description

Initiates a device restart.

## -parameters

### -param pbSuccess 

[out, retval]
True if the operation succeeds; otherwise, false.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

From a SetupDi interface perspective, this will translate to a DICS_PROPCHANGE.   
See the MSDN docs for details.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtfpnpaction/nn-wdtfpnpaction-iwdtfpnpaction2">IWDTFPNPAction2</a>
