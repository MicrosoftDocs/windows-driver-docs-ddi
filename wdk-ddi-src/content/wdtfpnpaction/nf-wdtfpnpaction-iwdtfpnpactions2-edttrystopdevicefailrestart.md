---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.EDTTryStopDeviceFailRestart
title: IWDTFPNPActions2::EDTTryStopDeviceFailRestart method
author: windows-driver-content
description: Attempts to send an IRP_MN_STOP_DEVICE event to the target device and then fail the subsequent device restart.
old-location: dtf\iwdtfpnpactions2_edttrystopdevicefailrestart.htm
old-project: dtf
ms.assetid: b205a0a4-a659-47ff-90d5-b1bb58983e36
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdtfpnpaction/IWDTFPNPActions2::EDTTryStopDeviceFailRestart, IWDTFPNPActions2 interface [Windows Device Testing Framework], EDTTryStopDeviceFailRestart method, IWDTFPNPActions2, IWDTFPNPActions2::EDTTryStopDeviceFailRestart, EDTTryStopDeviceFailRestart, EDTTryStopDeviceFailRestart method [Windows Device Testing Framework], IWDTFPNPActions2 interface, dtf.iwdtfpnpactions2_edttrystopdevicefailrestart, EDTTryStopDeviceFailRestart method [Windows Device Testing Framework]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: wdtfpnpaction.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wdtfpnpaction.h
apiname:
-	IWDTFPNPActions2.EDTTryStopDeviceFailRestart
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFPNPActions2::EDTTryStopDeviceFailRestart method


## -description


Attempts to send an IRP_MN_STOP_DEVICE event to the target device and 
then fail the subsequent device restart.


## -syntax


````
HRESULT EDTTryStopDeviceFailRestart(
  [out, retval] VARIANT_BOOL *pbSuccess
);
````


## -parameters




### -param pbSuccess [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



<div class="alert"><b>Note</b>  The <a href="https://msdn.microsoft.com/8fc225af-09d4-42a0-a862-4af89addd5f8">IWDTFEnhancedDeviceTestSupportAction2::Enable</a>  
method must be called for the target device before calling this method.</div>
<div> </div>
<b>EDTTryStopDeviceFailRestart</b> attempts to trigger a PnP resource 
rebalance (an Query Stop, Stop, Start IRP sequence) in which it fails the IRP_MN_START_DEVICE event 
which follows a successful Query Stop and Stop. The failed Start IRP, in turn, causes the system 
to surprise remove the device (IRP_MN_SURPRISE_REMOVAL).

The Stop IRP is not guaranteed. Other drivers on the stack can fail an 
IRP_MN_QUERY_STOP_DEVICE event which precedes the Stop IRP (resulting in IRP_MN_CANCEL_STOP_DEVICE). 
Also, the system may optimize if it detects that the target device does not use hardware 
resources (e.g. a USB mouse) and send a CancelStop IRP instead.

If your device does not consume hardware resources but you still wish to attempt to test 
how the drivers and applications handle the PnP resource rebalance with a failed start, you can 
instead run the <b>EDTTryStopDeviceFailRestart</b> method on a parent 
device, grandparent, etc., which does consume hardware resources. For example, if your device 
is a USB mouse, you can run this method on the parent USB controller instead.




## -see-also

<a href="..\wdtfpnpaction\nn-wdtfpnpaction-iwdtfpnpactions2.md">IWDTFPNPActions2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFPNPActions2::EDTTryStopDeviceFailRestart method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

