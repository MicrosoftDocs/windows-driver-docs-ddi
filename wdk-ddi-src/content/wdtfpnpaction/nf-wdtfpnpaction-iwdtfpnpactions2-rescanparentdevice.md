---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.RescanParentDevice
title: IWDTFPNPActions2::RescanParentDevice (wdtfpnpaction.h)
description: Rescans and re-enumerates the target device's parent device.
old-location: dtf\iwdtfpnpactions2_rescanparentdevice.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFPNPActions2::RescanParentDevice"]
ms.keywords: IWDTFPNPActions2 interface [Windows Device Testing Framework],RescanParentDevice method, IWDTFPNPActions2.RescanParentDevice, IWDTFPNPActions2::RescanParentDevice, RescanParentDevice, RescanParentDevice method [Windows Device Testing Framework], RescanParentDevice method [Windows Device Testing Framework],IWDTFPNPActions2 interface, dtf.iwdtfpnpactions2_rescanparentdevice, wdtfpnpaction/IWDTFPNPActions2::RescanParentDevice
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFPNPActions2::RescanParentDevice
 - wdtfpnpaction/IWDTFPNPActions2::RescanParentDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wdtfpnpaction.h
api_name:
 - IWDTFPNPActions2.RescanParentDevice
---

# IWDTFPNPActions2::RescanParentDevice


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


