---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.EDTCancelStopDevice
title: IWDTFPNPActions2::EDTCancelStopDevice
description: Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device.
old-location: dtf\iwdtfpnpactions2_edtcancelstopdevice.htm
tech.root: dtf
ms.assetid: b0616c88-1304-4d39-b7bd-e7d1355a9de6
ms.date: 04/04/2018
ms.keywords: EDTCancelStopDevice, EDTCancelStopDevice method [Windows Device Testing Framework], EDTCancelStopDevice method [Windows Device Testing Framework],IWDTFPNPActions2 interface, IWDTFPNPActions2 interface [Windows Device Testing Framework],EDTCancelStopDevice method, IWDTFPNPActions2.EDTCancelStopDevice, IWDTFPNPActions2::EDTCancelStopDevice, dtf.iwdtfpnpactions2_edtcancelstopdevice, wdtfpnpaction/IWDTFPNPActions2::EDTCancelStopDevice
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
req.lib: 
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
-	IWDTFPNPActions2.EDTCancelStopDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFPNPActions2::EDTCancelStopDevice


## -description


Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device.


## -parameters




### -param pbSuccess [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



<div class="alert"><b>Note</b>  The <a href="https://msdn.microsoft.com/8fc225af-09d4-42a0-a862-4af89addd5f8">IWDTFEnhancedDeviceTestSupportAction2::Enable</a>  
method must be called for the target device before calling this method.</div>
<div> </div>
<b>EDTCancelStopDevice</b> attempts to trigger an IRP_MN_CANCEL_STOP_DEVICE 
event by causing the system to send an IRP_MN_QUERY_STOP_DEVICE event and by intentionally failing 
the query IRP in the DeviceManagement2 helper driver.

It is possible for the filter drivers that are loaded above the helper driver 
to fail the query IRP as well. In that case, the helper driver will indicate this condition 
by setting EDTRS_QueryStopVetoed in ppResult.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451094">IWDTFPNPActions2</a>
 

 

