---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.RescanDevice
title: IWDTFPNPAction2::RescanDevice (wdtfpnpaction.h)
description: Rescans the target device.
old-location: dtf\iwdtfpnpaction2_rescandevice.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFPNPAction2::RescanDevice"]
ms.keywords: IWDTFPNPAction2 interface [Windows Device Testing Framework],RescanDevice method, IWDTFPNPAction2.RescanDevice, IWDTFPNPAction2::RescanDevice, Microsoft.WDTF.IWDTFPNPAction2.RescanDevice, Microsoft::WDTF::IWDTFPNPAction2::RescanDevice, RescanDevice, RescanDevice method [Windows Device Testing Framework], RescanDevice method [Windows Device Testing Framework],IWDTFPNPAction2 interface, dtf.iwdtfpnpaction2_rescandevice, wdtfpnpaction/IWDTFPNPAction2::RescanDevice
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
 - IWDTFPNPAction2::RescanDevice
 - wdtfpnpaction/IWDTFPNPAction2::RescanDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFDriverPNPAction.Interop.dll
api_name:
 - IWDTFPNPAction2.RescanDevice
---

# IWDTFPNPAction2::RescanDevice


## -description

Rescans the target device.

## -parameters

### -param pbSuccess 

[out, retval]
True if the operation succeeds; otherwise, false.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtfpnpaction/nn-wdtfpnpaction-iwdtfpnpaction2">IWDTFPNPAction2</a>
