---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.EDTCancelStopDevice
title: IWDTFPNPAction2::EDTCancelStopDevice method
author: windows-driver-content
description: Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device.
old-location: dtf\iwdtfpnpaction2_edtcancelstopdevice.htm
old-project: dtf
ms.assetid: 5ddce998-2f64-4711-b820-5baa88096d99
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: Microsoft.WDTF.IWDTFPNPAction2.EDTCancelStopDevice, EDTCancelStopDevice method [Windows Device Testing Framework], IWDTFPNPAction2 interface, IWDTFPNPAction2, wdtfpnpaction/IWDTFPNPAction2::EDTCancelStopDevice, dtf.iwdtfpnpaction2_edtcancelstopdevice, IWDTFPNPAction2::EDTCancelStopDevice, Microsoft::WDTF::IWDTFPNPAction2::EDTCancelStopDevice, IWDTFPNPAction2 interface [Windows Device Testing Framework], EDTCancelStopDevice method, EDTCancelStopDevice, EDTCancelStopDevice method [Windows Device Testing Framework]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: wdtfpnpaction.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFDriverPNPAction.Interop.dll
apiname:
-	IWDTFPNPAction2.EDTCancelStopDevice
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFPNPAction2::EDTCancelStopDevice method


## -description


Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device.


## -syntax


````
HRESULT EDTCancelStopDevice(
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
<b>EDTCancelStopDevice</b> attempts to trigger an IRP_MN_CANCEL_STOP_DEVICE 
event by causing the system to send an IRP_MN_QUERY_STOP_DEVICE event and by intentionally failing 
the query IRP in the DeviceManagement2 helper driver.

It is possible for the filter drivers that are loaded above the helper driver 
to fail the query IRP as well. In that case, the helper driver will indicate this condition 
by setting EDTRS_QueryStopVetoed in ppResult.




## -see-also

<a href="..\wdtfpnpaction\nn-wdtfpnpaction-iwdtfpnpaction2.md">IWDTFPNPAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFPNPAction2::EDTCancelStopDevice method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

