---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.EDTTryStopDeviceRequestNewResources
title: IWDTFPNPActions2::EDTTryStopDeviceRequestNewResources (wdtfpnpaction.h)
description: Attempts to send an IRP_MN_STOP_DEVICE event to the target device and assign new resources to the target device.
old-location: dtf\iwdtfpnpactions2_edttrystopdevicerequestnewresources.htm
tech.root: dtf
ms.assetid: 20f1ff95-55d3-46d2-816b-edf2b42e6e86
ms.date: 04/04/2018
ms.keywords: EDTTryStopDeviceRequestNewResources, EDTTryStopDeviceRequestNewResources method [Windows Device Testing Framework], EDTTryStopDeviceRequestNewResources method [Windows Device Testing Framework],IWDTFPNPActions2 interface, IWDTFPNPActions2 interface [Windows Device Testing Framework],EDTTryStopDeviceRequestNewResources method, IWDTFPNPActions2.EDTTryStopDeviceRequestNewResources, IWDTFPNPActions2::EDTTryStopDeviceRequestNewResources, dtf.iwdtfpnpactions2_edttrystopdevicerequestnewresources, wdtfpnpaction/IWDTFPNPActions2::EDTTryStopDeviceRequestNewResources
ms.topic: method
f1_keywords:
 - "wdtfpnpaction/IWDTFPNPActions2.EDTTryStopDeviceRequestNewResources"
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
- IWDTFPNPActions2.EDTTryStopDeviceRequestNewResources
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFPNPActions2::EDTTryStopDeviceRequestNewResources


## -description


Attempts to send an IRP_MN_STOP_DEVICE event to the target device and 
assign new resources to the target device.


## -parameters




### -param pbSuccess [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



<div class="alert"><b>Note</b>  The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfedtaction/nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-enable">IWDTFEnhancedDeviceTestSupportAction2::Enable</a>  
method must be called for the target device before calling this method.</div>
<div> </div>
Similar to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfpnpaction/nf-wdtfpnpaction-iwdtfpnpaction2-edttrystopdevice">EDTTryStopDevice</a> method, 
<b>EDTTryStopDeviceRequestNewResources</b> attempts to trigger a PnP resource 
rebalance (e.g. IRP_MN_STOP_DEVICE) on the target device stack, with the addition that the method 
attempts to force the device onto a new set of hardware resources.

The Stop IRP is not guaranteed. Other drivers on the stack can fail the IRP_MN_QUERY_STOP_DEVICE event
which precedes the Stop IRP (resulting in IRP_MN_CANCEL_STOP_DEVICE). Also, the system may 
optimize if it detects that the target device does not use hardware resources (e.g. a USB mouse) 
and send a CancelStop IRP instead.

If your device does not consume hardware resources but you still wish to attempt to test 
how the drivers and applications handle the PnP resource rebalance, you can instead run 
<b>EDTTryStopDeviceRequestNewResources</b> on a parent device, grandparent, 
etc., which does consume hardware resources. For example, if your device is a USB mouse, you can 
run this method on the parent USB controller instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">IWDTFPNPActions2</a>
 

 

