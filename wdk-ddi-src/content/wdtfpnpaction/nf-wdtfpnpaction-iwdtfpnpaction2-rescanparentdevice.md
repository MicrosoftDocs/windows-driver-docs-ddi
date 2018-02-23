---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.RescanParentDevice
title: IWDTFPNPAction2::RescanParentDevice method
author: windows-driver-content
description: Rescans and re-enumerates the target device's parent device.
old-location: dtf\iwdtfpnpaction2_rescanparentdevice.htm
old-project: dtf
ms.assetid: 5b25cffa-df53-49d5-be26-1901eddfdad2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: dtf.iwdtfpnpaction2_rescanparentdevice, RescanParentDevice method [Windows Device Testing Framework], IWDTFPNPAction2 interface, RescanParentDevice, RescanParentDevice method [Windows Device Testing Framework], IWDTFPNPAction2::RescanParentDevice, IWDTFPNPAction2, IWDTFPNPAction2 interface [Windows Device Testing Framework], RescanParentDevice method, Microsoft::WDTF::IWDTFPNPAction2::RescanParentDevice, Microsoft.WDTF.IWDTFPNPAction2.RescanParentDevice, wdtfpnpaction/IWDTFPNPAction2::RescanParentDevice
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
-	IWDTFPNPAction2.RescanParentDevice
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFPNPAction2::RescanParentDevice method


## -description


Rescans and re-enumerates the target device's parent device.


## -syntax


````
HRESULT RescanParentDevice(
  [out, retval] VARIANT_BOOL *pbSuccess
);
````


## -parameters




### -param pbSuccess [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



In essence, <b>RescanParentDevice</b> calls 
<b>CM_Reenumerate_DevNode()</b>. See the MSDN documentation for 
<b>CM_Reenumerate_DevNode()</b>.




## -see-also

<a href="..\wdtfpnpaction\nn-wdtfpnpaction-iwdtfpnpaction2.md">IWDTFPNPAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFPNPAction2::RescanParentDevice method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

