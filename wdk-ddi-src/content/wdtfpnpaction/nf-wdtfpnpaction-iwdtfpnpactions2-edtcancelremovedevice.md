---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.EDTCancelRemoveDevice
title: IWDTFPNPActions2::EDTCancelRemoveDevice (wdtfpnpaction.h)
description: Sends an IRP_MN_CANCEL_REMOVE_DEVICE event to the target device.
old-location: dtf\iwdtfpnpactions2_edtcancelremovedevice.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFPNPActions2::EDTCancelRemoveDevice"]
ms.keywords: EDTCancelRemoveDevice, EDTCancelRemoveDevice method [Windows Device Testing Framework], EDTCancelRemoveDevice method [Windows Device Testing Framework],IWDTFPNPActions2 interface, IWDTFPNPActions2 interface [Windows Device Testing Framework],EDTCancelRemoveDevice method, IWDTFPNPActions2.EDTCancelRemoveDevice, IWDTFPNPActions2::EDTCancelRemoveDevice, dtf.iwdtfpnpactions2_edtcancelremovedevice, wdtfpnpaction/IWDTFPNPActions2::EDTCancelRemoveDevice
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
 - IWDTFPNPActions2::EDTCancelRemoveDevice
 - wdtfpnpaction/IWDTFPNPActions2::EDTCancelRemoveDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wdtfpnpaction.h
api_name:
 - IWDTFPNPActions2.EDTCancelRemoveDevice
---

# IWDTFPNPActions2::EDTCancelRemoveDevice


## -description

Sends an IRP_MN_CANCEL_REMOVE_DEVICE event to the target device.

## -parameters

### -param pbSuccess 

[out, retval]
True if the operation succeeds; otherwise, false.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

<div class="alert"><b>Note</b>  The <a href="/windows-hardware/drivers/ddi/wdtfedtaction/nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-enable">IWDTFEnhancedDeviceTestSupportAction2::Enable</a>  
method must be called for the target device before calling this method.</div>
<div> </div>
<b>EDTCancelRemoveDevice</b> triggers an IRP_MN_CANCEL_REMOVE event
by intentionally failing an IRP_MN_QUERY_REMOVE_DEVICE event.


