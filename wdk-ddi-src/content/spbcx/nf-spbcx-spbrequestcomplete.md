---
UID: NF:spbcx.SpbRequestComplete
title: SpbRequestComplete function (spbcx.h)
description: The SpbRequestComplete method completes an I/O request and supplies a completion status.
old-location: spb\spbrequestcomplete.htm
tech.root: SPB
ms.assetid: 356BC81E-8FE9-4BC7-83E5-20A64D149A0D
ms.date: 04/30/2018
ms.keywords: SPB.spbrequestcomplete, SpbRequestComplete, SpbRequestComplete method [Buses], spbcx/SpbRequestComplete
f1_keywords:
 - "spbcx/SpbRequestComplete"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- spbcxstubs.lib
- spbcxstubs.dll
api_name:
- SpbRequestComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# SpbRequestComplete function


## -description


The <b>SpbRequestComplete</b> method completes an I/O request and supplies a completion status.


## -parameters




### -param Request [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request to complete. The SPB controller driver previously received this handle through one of its registered <a href="https://docs.microsoft.com/previous-versions/hh450911(v=vs.85)">event callback functions</a>.


### -param CompletionStatus [in]

An NTSTATUS value that represents the completion status of the request. Valid status values include, but are not limited to, the following:





#### STATUS_SUCCESS

The I/O request completed successfully.



#### STATUS_CANCELLED

The I/O request is canceled.



#### STATUS_UNSUCCESSFUL

The driver encountered an error while processing the I/O request.


## -remarks



Your controller driver calls this method to complete an I/O request that it previously received during one of the following callbacks:

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_other">EvtSpbControllerIoOther</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_read">EvtSpbControllerIoRead</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_sequence">EvtSpbControllerIoSequence</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_write">EvtSpbControllerIoWrite</a>
Call <b>SpbRequestComplete</b> instead of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> method to complete I/O requests received by the callback functions in the preceding list.

A bug check occurs if the caller supplies an invalid SPBREQUEST handle.

A call to <b>SpbRequestComplete</b> represents the final stage in the processing of an I/O request. When this method returns, the <i>Request</i> handle value is no longer valid.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_other">EvtSpbControllerIoOther</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_read">EvtSpbControllerIoRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_sequence">EvtSpbControllerIoSequence</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_write">EvtSpbControllerIoWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>
 

 

