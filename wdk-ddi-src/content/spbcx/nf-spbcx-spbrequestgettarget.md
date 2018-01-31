---
UID: NF:spbcx.SpbRequestGetTarget
title: SpbRequestGetTarget function
author: windows-driver-content
description: The SpbRequestGetTarget method retrieves the SPBTARGET handle from the specified I/O request.
old-location: spb\spbrequestgettarget.htm
old-project: SPB
ms.assetid: 2F89C886-99FF-4D6C-B52F-6422DB9E76AE
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: spbcx/SpbRequestGetTarget, SPB.spbrequestgettarget, SpbRequestGetTarget, SpbRequestGetTarget method [Buses]
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
-	SpbRequestGetTarget
product: Windows
targetos: Windows
req.typenames: SPB_REQUEST_TYPE, *PSPB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# SpbRequestGetTarget function


## -description


The <b>SpbRequestGetTarget</b> method retrieves the SPBTARGET handle from the specified I/O request.


## -syntax


````
SPBTARGET SpbRequestGetTarget(
  _In_ SPBREQUEST SpbRequest
);
````


## -parameters




#### - SpbRequest [in]

An <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request. The SPB controller driver previously received this handle through one of its registered <a href="https://msdn.microsoft.com/1DA1FF41-FB01-45CC-B0C1-EAF2C81D0CDA">event callback functions</a>.


## -returns


<b>SpbRequestGetTarget</b> returns an <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target device on the bus for the specified I/O request.



## -remarks


The returned SPBTARGET handle is guaranteed to remain valid until the corresponding I/O request is completed.



## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SpbRequestGetTarget method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

