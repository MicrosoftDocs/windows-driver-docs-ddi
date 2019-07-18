---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.EDTTryStopDevice
title: IWDTFPNPAction2::EDTTryStopDevice (wdtfpnpaction.h)
description: Attempts to send an IRP_MN_STOP_DEVICE event to the target device.
old-location: dtf\iwdtfpnpaction2_edttrystopdevice.htm
tech.root: dtf
ms.assetid: 6a10f86e-163d-4307-b830-5c90e5cb1c45
ms.date: 04/04/2018
ms.keywords: EDTTryStopDevice, EDTTryStopDevice method [Windows Device Testing Framework], EDTTryStopDevice method [Windows Device Testing Framework],IWDTFPNPAction2 interface, IWDTFPNPAction2 interface [Windows Device Testing Framework],EDTTryStopDevice method, IWDTFPNPAction2.EDTTryStopDevice, IWDTFPNPAction2::EDTTryStopDevice, Microsoft.WDTF.IWDTFPNPAction2.EDTTryStopDevice, Microsoft::WDTF::IWDTFPNPAction2::EDTTryStopDevice, dtf.iwdtfpnpaction2_edttrystopdevice, wdtfpnpaction/IWDTFPNPAction2::EDTTryStopDevice
ms.topic: method
f1_keywords:
 - "wdtfpnpaction/IWDTFPNPAction2.EDTTryStopDevice"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTFDriverPNPAction.Interop.dll
api_name:
- IWDTFPNPAction2.EDTTryStopDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFPNPAction2::EDTTryStopDevice


## -description


Attempts to send an IRP_MN_STOP_DEVICE event to the target device.


## -parameters




### -param pbSuccess [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



<div class="alert"><b>Note</b>  The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfedtaction/nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-enable">IWDTFEnhancedDeviceTestSupportAction2::Enable</a>  
method must be called for the target device before calling this method.</div>
<div> </div>
<b>EDTTryStopDevice</b> attempts to trigger a PnP resource 
rebalance (e.g. IRP_MN_STOP_DEVICE) on the target device stack. The Stop IRP is not guaranteed. 
Other drivers on the stack can fail the IRP_MN_QUERY_STOP_DEVICE event which precedes the Stop IRP 
(resulting in an IRP_MN_CANCEL_STOP_DEVICE event). Also, the system may optimize if it detects 
that the target device does not use hardware resources (e.g. a USB mouse) and send a 
CancelStop IRP instead.

If your device does not consume hardware resources but you still wish to attempt to test how 
the drivers and applications handle the PnP resource rebalance, you can instead run the 
<b>EDTTryStopDevice</b> method on a parent device, grandparent, etc., 
which does consume hardware resources. For example, if your device is a USB mouse, you can run 
<b>EDTTryStopDevice</b> on the parent USB controller instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfpnpaction/nn-wdtfpnpaction-iwdtfpnpaction2">IWDTFPNPAction2</a>
 

 

