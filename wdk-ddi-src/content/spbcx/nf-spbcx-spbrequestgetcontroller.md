---
UID: NF:spbcx.SpbRequestGetController
title: SpbRequestGetController function
author: windows-driver-content
description: The SpbRequestGetController method returns the WDFDEVICE handle to the device object for the SPB controller that the specified I/O request was sent to.
old-location: spb\spbrequestgetcontroller.htm
old-project: SPB
ms.assetid: 0CD692E2-B2D6-4786-8C0B-C0DCAFCF6259
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SPB.spbrequestgetcontroller, SpbRequestGetController method [Buses], SpbRequestGetController, spbcx/SpbRequestGetController
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: spbcx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Spbcxstubs.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	spbcxstubs.lib
-	spbcxstubs.dll
apiname:
-	SpbRequestGetController
product: Windows
targetos: Windows
req.typenames: SPB_REQUEST_TYPE, *PSPB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# SpbRequestGetController function


## -description


The <b>SpbRequestGetController</b> method returns the WDFDEVICE handle to the device object for the SPB controller that the specified I/O request was sent to.


## -syntax


````
WDFDEVICE SpbRequestGetController(
  _In_ SPBREQUEST SpbRequest
);
````


## -parameters




### -param SpbRequest [in]

The <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request from which to retrieve the WDFDEVICE handle. The SPB controller driver previously received this handle through one of its registered <a href="https://msdn.microsoft.com/1DA1FF41-FB01-45CC-B0C1-EAF2C81D0CDA">event callback functions</a>.


## -returns



<b>SpbRequestGetController</b> returns the WDFDEVICE handle that the I/O request was sent to.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SpbRequestGetController method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

