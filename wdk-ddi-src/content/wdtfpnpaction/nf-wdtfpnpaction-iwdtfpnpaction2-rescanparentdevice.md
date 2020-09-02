---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.RescanParentDevice
title: IWDTFPNPAction2::RescanParentDevice (wdtfpnpaction.h)
description: Rescans and re-enumerates the target device's parent device.
old-location: dtf\iwdtfpnpaction2_rescanparentdevice.htm
tech.root: dtf
ms.assetid: 5b25cffa-df53-49d5-be26-1901eddfdad2
ms.date: 04/04/2018
keywords: ["IWDTFPNPAction2::RescanParentDevice"]
ms.keywords: IWDTFPNPAction2 interface [Windows Device Testing Framework],RescanParentDevice method, IWDTFPNPAction2.RescanParentDevice, IWDTFPNPAction2::RescanParentDevice, Microsoft.WDTF.IWDTFPNPAction2.RescanParentDevice, Microsoft::WDTF::IWDTFPNPAction2::RescanParentDevice, RescanParentDevice, RescanParentDevice method [Windows Device Testing Framework], RescanParentDevice method [Windows Device Testing Framework],IWDTFPNPAction2 interface, dtf.iwdtfpnpaction2_rescanparentdevice, wdtfpnpaction/IWDTFPNPAction2::RescanParentDevice
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
 - IWDTFPNPAction2::RescanParentDevice
 - wdtfpnpaction/IWDTFPNPAction2::RescanParentDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFDriverPNPAction.Interop.dll
api_name:
 - IWDTFPNPAction2.RescanParentDevice
---

# IWDTFPNPAction2::RescanParentDevice


## -description

Rescans and re-enumerates the target device's parent device.

## -parameters

### -param pbSuccess 

[out, retval]
True if the operation succeeds; otherwise, false.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

In essence, <b>RescanParentDevice</b> calls 
<b>CM_Reenumerate_DevNode()</b>. See the MSDN documentation for 
<b>CM_Reenumerate_DevNode()</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfpnpaction/nn-wdtfpnpaction-iwdtfpnpaction2">IWDTFPNPAction2</a>

