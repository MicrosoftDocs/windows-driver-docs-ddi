---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.EDTCancelStopDevice
title: IWDTFPNPActions2::EDTCancelStopDevice (wdtfpnpaction.h)
description: Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device.
old-location: dtf\iwdtfpnpactions2_edtcancelstopdevice.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFPNPActions2::EDTCancelStopDevice"]
ms.keywords: EDTCancelStopDevice, EDTCancelStopDevice method [Windows Device Testing Framework], EDTCancelStopDevice method [Windows Device Testing Framework],IWDTFPNPActions2 interface, IWDTFPNPActions2 interface [Windows Device Testing Framework],EDTCancelStopDevice method, IWDTFPNPActions2.EDTCancelStopDevice, IWDTFPNPActions2::EDTCancelStopDevice, dtf.iwdtfpnpactions2_edtcancelstopdevice, wdtfpnpaction/IWDTFPNPActions2::EDTCancelStopDevice
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
 - IWDTFPNPActions2::EDTCancelStopDevice
 - wdtfpnpaction/IWDTFPNPActions2::EDTCancelStopDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wdtfpnpaction.h
api_name:
 - IWDTFPNPActions2.EDTCancelStopDevice
---

# IWDTFPNPActions2::EDTCancelStopDevice


## -description

Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device.

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
<b>EDTCancelStopDevice</b> attempts to trigger an IRP_MN_CANCEL_STOP_DEVICE 
event by causing the system to send an IRP_MN_QUERY_STOP_DEVICE event and by intentionally failing 
the query IRP in the DeviceManagement2 helper driver.

It is possible for the filter drivers that are loaded above the helper driver 
to fail the query IRP as well. In that case, the helper driver will indicate this condition 
by setting EDTRS_QueryStopVetoed in ppResult.


