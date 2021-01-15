---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.EDTSurpriseRemoveDevice
title: IWDTFPNPAction2::EDTSurpriseRemoveDevice (wdtfpnpaction.h)
description: Sends an IRP_MN_SURPRISE_REMOVAL event to the target device.
old-location: dtf\iwdtfpnpaction2_edtsurpriseremovedevice.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFPNPAction2::EDTSurpriseRemoveDevice"]
ms.keywords: EDTSurpriseRemoveDevice, EDTSurpriseRemoveDevice method [Windows Device Testing Framework], EDTSurpriseRemoveDevice method [Windows Device Testing Framework],IWDTFPNPAction2 interface, IWDTFPNPAction2 interface [Windows Device Testing Framework],EDTSurpriseRemoveDevice method, IWDTFPNPAction2.EDTSurpriseRemoveDevice, IWDTFPNPAction2::EDTSurpriseRemoveDevice, Microsoft.WDTF.IWDTFPNPAction2.EDTSurpriseRemoveDevice, Microsoft::WDTF::IWDTFPNPAction2::EDTSurpriseRemoveDevice, dtf.iwdtfpnpaction2_edtsurpriseremovedevice, wdtfpnpaction/IWDTFPNPAction2::EDTSurpriseRemoveDevice
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
 - IWDTFPNPAction2::EDTSurpriseRemoveDevice
 - wdtfpnpaction/IWDTFPNPAction2::EDTSurpriseRemoveDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFDriverPNPAction.Interop.dll
api_name:
 - IWDTFPNPAction2::EDTSurpriseRemoveDevice
---

# IWDTFPNPAction2::EDTSurpriseRemoveDevice


## -description

Sends an IRP_MN_SURPRISE_REMOVAL event to the target device.

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
<b>EDTSurpriseRemoveDevice</b> attempts to trigger a surprise removal of the target device. 
This operation is useful for testing 
how drivers and driver/device aware applications handle the IRP_MN_SURPRISE_REMOVAL event, e.g. scenarios in which 
the device unexpectedly fails or is removed.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtfpnpaction/nn-wdtfpnpaction-iwdtfpnpaction2">IWDTFPNPAction2</a>

