---
UID: NF:stiusd.IStiUSD.Diagnostic
title: IStiUSD::Diagnostic method
author: windows-driver-content
description: A still image minidriver's IStiUSD::Diagnostic method runs diagnostic tests on a still image device.
old-location: image\istiusd_diagnostic.htm
old-project: image
ms.assetid: bf99c34e-5a71-4f2b-8dca-bed87d18b352
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: IStiUSD, IStiUSD::Diagnostic, Diagnostic
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: stiusd.h
req.include-header: Stiusd.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IStiUSD.Diagnostic
req.alt-loc: stiusd.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---

# IStiUSD::Diagnostic method



## -description
A still image minidriver's <b>IStiUSD::Diagnostic</b> method runs diagnostic tests on a still image device.



## -syntax

````
HRESULT Diagnostic(
   LPSTI_DIAG pBuffer
);
````


## -parameters

### -param pBuffer 

Caller-supplied pointer to an <a href="..\sti\ns-sti-_sti_diag.md">STI_DIAG</a> structure to receive testing status information.


## -returns
If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.


## -remarks
The <b>IStiUSD::Diagnostic</b> method is called when a user clicks on the Scanners and Cameras Control Panel's Test button. The method should execute tests to confirm that the device is fully operational. For a scanner, these tests might include turning the light on and off, and moving the scanning arm. For a camera, they might include execution of built-in diagnostic functions, or manipulation of device settings. The return value should indicate success or failure of the diagnostic tests.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543736">IStiDevice::Diagnostic</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiUSD::Diagnostic method%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

