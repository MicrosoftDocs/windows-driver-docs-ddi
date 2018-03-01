---
UID: NF:spbcx.SpbRequestComplete
title: SpbRequestComplete function
author: windows-driver-content
description: The SpbRequestComplete method completes an I/O request and supplies a completion status.
old-location: spb\spbrequestcomplete.htm
old-project: SPB
ms.assetid: 356BC81E-8FE9-4BC7-83E5-20A64D149A0D
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SPB.spbrequestcomplete, SpbRequestComplete, SpbRequestComplete method [Buses], spbcx/SpbRequestComplete
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	spbcxstubs.lib
-	spbcxstubs.dll
api_name:
-	SpbRequestComplete
product: Windows
targetos: Windows
req.typenames: SPB_REQUEST_TYPE, *PSPB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# SpbRequestComplete function


## -description


The <b>SpbRequestComplete</b> method completes an I/O request and supplies a completion status.


## -syntax


````
VOID SpbRequestComplete(
  _In_ SPBREQUEST Request,
  _In_ NTSTATUS   CompletionStatus
);
````


## -parameters




### -param Request [in]

An <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request to complete. The SPB controller driver previously received this handle through one of its registered <a href="https://msdn.microsoft.com/1DA1FF41-FB01-45CC-B0C1-EAF2C81D0CDA">event callback functions</a>.


### -param CompletionStatus [in]

An NTSTATUS value that represents the completion status of the request. Valid status values include, but are not limited to, the following:





#### STATUS_SUCCESS

The I/O request completed successfully.



#### STATUS_CANCELLED

The I/O request is canceled.



#### STATUS_UNSUCCESSFUL

The driver encountered an error while processing the I/O request.


## -returns



None.




## -remarks



Your controller driver calls this method to complete an I/O request that it previously received during one of the following callbacks:

<a href="https://msdn.microsoft.com/5A4BC061-4703-4C46-BD5D-A891F3DA8842">EvtSpbControllerIoOther</a>
<a href="https://msdn.microsoft.com/2BC0E6E7-7EE1-487A-9276-AE8EBB3FFD43">EvtSpbControllerIoRead</a>
<a href="https://msdn.microsoft.com/C56F1528-5FDA-4BC9-AB32-7882FB0F7713">EvtSpbControllerIoSequence</a>
<a href="https://msdn.microsoft.com/D97C3A17-309E-4364-8DFB-9073901D332E">EvtSpbControllerIoWrite</a>
Call <b>SpbRequestComplete</b> instead of the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> method to complete I/O requests received by the callback functions in the preceding list.

A bug check occurs if the caller supplies an invalid SPBREQUEST handle.

A call to <b>SpbRequestComplete</b> represents the final stage in the processing of an I/O request. When this method returns, the <i>Request</i> handle value is no longer valid.




## -see-also

<a href="https://msdn.microsoft.com/2BC0E6E7-7EE1-487A-9276-AE8EBB3FFD43">EvtSpbControllerIoRead</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>



<a href="https://msdn.microsoft.com/D97C3A17-309E-4364-8DFB-9073901D332E">EvtSpbControllerIoWrite</a>



<a href="https://msdn.microsoft.com/C56F1528-5FDA-4BC9-AB32-7882FB0F7713">EvtSpbControllerIoSequence</a>



<a href="https://msdn.microsoft.com/5A4BC061-4703-4C46-BD5D-A891F3DA8842">EvtSpbControllerIoOther</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SpbRequestComplete method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

