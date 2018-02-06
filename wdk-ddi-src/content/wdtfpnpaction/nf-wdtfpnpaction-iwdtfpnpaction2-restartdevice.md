---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.RestartDevice
title: IWDTFPNPAction2::RestartDevice method
author: windows-driver-content
description: Initiates a device restart.
old-location: dtf\iwdtfpnpaction2_restartdevice.htm
old-project: dtf
ms.assetid: 6023ca71-47ce-4add-891f-e125252ace08
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RestartDevice method [Windows Device Testing Framework], Microsoft::WDTF::IWDTFPNPAction2::RestartDevice, wdtfpnpaction/IWDTFPNPAction2::RestartDevice, RestartDevice, Microsoft.WDTF.IWDTFPNPAction2.RestartDevice, IWDTFPNPAction2, RestartDevice method [Windows Device Testing Framework], IWDTFPNPAction2 interface, dtf.iwdtfpnpaction2_restartdevice, IWDTFPNPAction2::RestartDevice, IWDTFPNPAction2 interface [Windows Device Testing Framework], RestartDevice method
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
-	IWDTFPNPAction2.RestartDevice
product: Windows
targetos: Windows
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
req.product: Windows 10 or later.
---

# IWDTFPNPAction2::RestartDevice method


## -description


Initiates a device restart.


## -syntax


````
HRESULT RestartDevice(
  [out, retval] VARIANT_BOOL *pbSuccess
);
````


## -parameters




### -param pbSuccess [out, retval]

True if the operation succeeds; otherwise, false.


## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



## -remarks


From a SetupDi interface perspective, this will translate to a DICS_PROPCHANGE.   
See the MSDN docs for details.



## -see-also

<a href="..\wdtfpnpaction\nn-wdtfpnpaction-iwdtfpnpaction2.md">IWDTFPNPAction2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFPNPAction2::RestartDevice method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

