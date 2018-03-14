---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.RequestEjectDevice
title: IWDTFPNPActions2::RequestEjectDevice method
author: windows-driver-content
description: Initiates a device eject.
old-location: dtf\iwdtfpnpactions2_requestejectdevice.htm
old-project: dtf
ms.assetid: 6c79b6e7-1134-4de6-b698-e09f295c3e84
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFPNPActions2, IWDTFPNPActions2 interface [Windows Device Testing Framework], RequestEjectDevice method, IWDTFPNPActions2::RequestEjectDevice, RequestEjectDevice method [Windows Device Testing Framework], RequestEjectDevice method [Windows Device Testing Framework], IWDTFPNPActions2 interface, RequestEjectDevice,IWDTFPNPActions2.RequestEjectDevice, dtf.iwdtfpnpactions2_requestejectdevice, wdtfpnpaction/IWDTFPNPActions2::RequestEjectDevice
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
-	IWDTFPNPActions2.RequestEjectDevice
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFPNPActions2::RequestEjectDevice method


## -description


Initiates a device eject.


## -syntax


````
HRESULT RequestEjectDevice(
  [out, retval] VARIANT_BOOL *pbSuccess
);
````


## -parameters




### -param pbSuccess [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



This will in essence call <b>CM_Request_Device_Eject()</b>. 
See the MSDN documentation for details.




## -see-also

<a href="..\wdtfpnpaction\nn-wdtfpnpaction-iwdtfpnpactions2.md">IWDTFPNPActions2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFPNPActions2::RequestEjectDevice method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

