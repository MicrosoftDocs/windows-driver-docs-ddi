---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.EDTSurpriseRemoveDevice
title: IWDTFPNPActions2::EDTSurpriseRemoveDevice method
author: windows-driver-content
description: Sends an IRP_MN_SURPRISE_REMOVAL event to the target device.
old-location: dtf\iwdtfpnpactions2_edtsurpriseremovedevice.htm
old-project: dtf
ms.assetid: 9f4511b8-c41f-4a7f-81e6-20c30a131f64
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: EDTSurpriseRemoveDevice method [Windows Device Testing Framework], EDTSurpriseRemoveDevice method [Windows Device Testing Framework], IWDTFPNPActions2 interface, EDTSurpriseRemoveDevice,IWDTFPNPActions2.EDTSurpriseRemoveDevice, IWDTFPNPActions2, IWDTFPNPActions2 interface [Windows Device Testing Framework], EDTSurpriseRemoveDevice method, IWDTFPNPActions2::EDTSurpriseRemoveDevice, dtf.iwdtfpnpactions2_edtsurpriseremovedevice, wdtfpnpaction/IWDTFPNPActions2::EDTSurpriseRemoveDevice
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	wdtfpnpaction.h
api_name:
-	IWDTFPNPActions2.EDTSurpriseRemoveDevice
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFPNPActions2::EDTSurpriseRemoveDevice method


## -description


Sends an IRP_MN_SURPRISE_REMOVAL event to the target device.


## -syntax


````
HRESULT EDTSurpriseRemoveDevice(
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
<b>EDTSurpriseRemoveDevice</b> attempts to trigger a surprise removal of the target device. 
This operation is useful for testing 
how drivers and driver/device aware applications handle the IRP_MN_SURPRISE_REMOVAL event, e.g. scenarios in which 
the device unexpectedly fails or is removed.




## -see-also

<a href="..\wdtfpnpaction\nn-wdtfpnpaction-iwdtfpnpactions2.md">IWDTFPNPActions2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFPNPActions2::EDTSurpriseRemoveDevice method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

