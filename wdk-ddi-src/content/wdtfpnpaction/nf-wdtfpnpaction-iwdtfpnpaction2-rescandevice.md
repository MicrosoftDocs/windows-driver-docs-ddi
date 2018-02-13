---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.RescanDevice
title: IWDTFPNPAction2::RescanDevice method
author: windows-driver-content
description: Rescans the target device.
old-location: dtf\iwdtfpnpaction2_rescandevice.htm
old-project: dtf
ms.assetid: 83288eab-020b-4870-9c99-b3215d52658c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RescanDevice, Microsoft.WDTF.IWDTFPNPAction2.RescanDevice, IWDTFPNPAction2, IWDTFPNPAction2::RescanDevice, RescanDevice method [Windows Device Testing Framework], IWDTFPNPAction2 interface, wdtfpnpaction/IWDTFPNPAction2::RescanDevice, IWDTFPNPAction2 interface [Windows Device Testing Framework], RescanDevice method, RescanDevice method [Windows Device Testing Framework], dtf.iwdtfpnpaction2_rescandevice, Microsoft::WDTF::IWDTFPNPAction2::RescanDevice
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
-	IWDTFPNPAction2.RescanDevice
product: Windows
targetos: Windows
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
req.product: Windows 10 or later.
---

# IWDTFPNPAction2::RescanDevice method


## -description


Rescans the target device.


## -syntax


````
HRESULT RescanDevice(
  [out, retval] VARIANT_BOOL *pbSuccess
);
````


## -parameters




### -param pbSuccess [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfpnpaction\nn-wdtfpnpaction-iwdtfpnpaction2.md">IWDTFPNPAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFPNPAction2::RescanDevice method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

