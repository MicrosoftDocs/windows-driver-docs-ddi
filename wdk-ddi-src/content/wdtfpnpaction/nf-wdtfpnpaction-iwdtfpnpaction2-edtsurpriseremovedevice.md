---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.EDTSurpriseRemoveDevice
title: IWDTFPNPAction2::EDTSurpriseRemoveDevice
author: windows-driver-content
description: Sends an IRP_MN_SURPRISE_REMOVAL event to the target device.
old-location: dtf\iwdtfpnpaction2_edtsurpriseremovedevice.htm
old-project: dtf
ms.assetid: 96bc080b-1ee2-4a32-be98-c58f6649e120
ms.author: windowsdriverdev
ms.date: 4/4/2018
ms.keywords: EDTSurpriseRemoveDevice, EDTSurpriseRemoveDevice method [Windows Device Testing Framework], EDTSurpriseRemoveDevice method [Windows Device Testing Framework],IWDTFPNPAction2 interface, IWDTFPNPAction2 interface [Windows Device Testing Framework],EDTSurpriseRemoveDevice method, IWDTFPNPAction2.EDTSurpriseRemoveDevice, IWDTFPNPAction2::EDTSurpriseRemoveDevice, Microsoft.WDTF.IWDTFPNPAction2.EDTSurpriseRemoveDevice, Microsoft::WDTF::IWDTFPNPAction2::EDTSurpriseRemoveDevice, dtf.iwdtfpnpaction2_edtsurpriseremovedevice, wdtfpnpaction/IWDTFPNPAction2::EDTSurpriseRemoveDevice
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFDriverPNPAction.Interop.dll
api_name:
-	IWDTFPNPAction2.EDTSurpriseRemoveDevice
product: Windows
targetos: Windows
req.typenames: 
---

# IWDTFPNPAction2::EDTSurpriseRemoveDevice


## -description


Sends an IRP_MN_SURPRISE_REMOVAL event to the target device.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451065">IWDTFPNPAction2</a>
 

 

