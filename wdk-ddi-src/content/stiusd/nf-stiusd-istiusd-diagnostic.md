---
UID: NF:stiusd.IStiUSD.Diagnostic
title: IStiUSD::Diagnostic (stiusd.h)
description: A still image minidriver's IStiUSD::Diagnostic method runs diagnostic tests on a still image device.
old-location: image\istiusd_diagnostic.htm
tech.root: image
ms.assetid: bf99c34e-5a71-4f2b-8dca-bed87d18b352
ms.date: 05/03/2018
ms.keywords: Diagnostic, Diagnostic method [Imaging Devices], Diagnostic method [Imaging Devices],IStiUSD interface, IStiUSD interface [Imaging Devices],Diagnostic method, IStiUSD.Diagnostic, IStiUSD::Diagnostic, image.istiusd_diagnostic, stifnc_07917e25-965a-4a7e-82af-1cfef09d6748.xml, stiusd/IStiUSD::Diagnostic
ms.topic: method
req.header: stiusd.h
req.include-header: Stiusd.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	stiusd.h
api_name:
-	IStiUSD.Diagnostic
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiUSD::Diagnostic


## -description


A still image minidriver's <b>IStiUSD::Diagnostic</b> method runs diagnostic tests on a still image device.


## -parameters




### -param pBuffer

Caller-supplied pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548383">STI_DIAG</a> structure to receive testing status information.


## -returns



If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStiUSD::Diagnostic</b> method is called when a user clicks on the Scanners and Cameras Control Panel's Test button. The method should execute tests to confirm that the device is fully operational. For a scanner, these tests might include turning the light on and off, and moving the scanning arm. For a camera, they might include execution of built-in diagnostic functions, or manipulation of device settings. The return value should indicate success or failure of the diagnostic tests.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543736">IStiDevice::Diagnostic</a>



<a href="https://msdn.microsoft.com/62740263-5bbb-48e1-be3d-9ee9cb37d6b9">IStiUSD</a>
 

 

