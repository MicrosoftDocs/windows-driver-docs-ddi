---
UID: NA:wdfrequest
ms.assetid: 10b9bec4-c13d-3d81-bf4f-3a6c11fa28b5
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfrequest.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfrequest.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_REQUEST_COMPLETION_PARAMS_INIT function](nf-wdfrequest-wdf_request_completion_params_init.md) | The WDF_REQUEST_COMPLETION_PARAMS_INIT function initializes a WDF_REQUEST_COMPLETION_PARAMS structure. |
| [WDF_REQUEST_FORWARD_OPTIONS_INIT function](nf-wdfrequest-wdf_request_forward_options_init.md) | The WDF_REQUEST_FORWARD_OPTIONS_INIT function initializes a WDF_REQUEST_FORWARD_OPTIONS structure. |
| [WDF_REQUEST_PARAMETERS_INIT function](nf-wdfrequest-wdf_request_parameters_init.md) | The WDF_REQUEST_PARAMETERS_INIT function initializes a WDF_REQUEST_PARAMETERS structure. |
| [WDF_REQUEST_REUSE_PARAMS_INIT function](nf-wdfrequest-wdf_request_reuse_params_init.md) | The WDF_REQUEST_REUSE_PARAMS_INIT function initializes a driver's WDF_REQUEST_REUSE_PARAMS structure. |
| [WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function](nf-wdfrequest-wdf_request_reuse_params_set_new_irp.md) | The WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function sets a new IRP in a driver's WDF_REQUEST_REUSE_PARAMS structure. |
| [WDF_REQUEST_SEND_OPTIONS_INIT function](nf-wdfrequest-wdf_request_send_options_init.md) | The WDF_REQUEST_SEND_OPTIONS_INIT function initializes a driver's WDF_REQUEST_SEND_OPTIONS structure. |
| [WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT function](nf-wdfrequest-wdf_request_send_options_set_timeout.md) | The WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT function sets a time-out value in a driver's WDF_REQUEST_SEND_OPTIONS structure. |
| [WdfRequestAllocateTimer function](nf-wdfrequest-wdfrequestallocatetimer.md) | The WdfRequestAllocateTimer method allocates a timer for a specified I/O request. |
| [WdfRequestCancelSentRequest function](nf-wdfrequest-wdfrequestcancelsentrequest.md) | The WdfRequestCancelSentRequest method attempts to cancel an I/O request that the caller previously submitted to an I/O target. |
| [WdfRequestChangeTarget function](nf-wdfrequest-wdfrequestchangetarget.md) | The WdfRequestChangeTarget method verifies that a specified I/O request can be sent to a specified I/O target. |
| [WdfRequestComplete function](nf-wdfrequest-wdfrequestcomplete.md) | The WdfRequestComplete method completes a specified I/O request and supplies a completion status. |
| [WdfRequestCompleteWithInformation function](nf-wdfrequest-wdfrequestcompletewithinformation.md) | The WdfRequestCompleteWithInformation method stores completion information and then completes a specified I/O request with a supplied completion status. |
| [WdfRequestCompleteWithPriorityBoost function](nf-wdfrequest-wdfrequestcompletewithpriorityboost.md) | The WdfRequestCompleteWithPriorityBoost method completes a specified I/O request and supplies a completion status. It also specifies a value that the system can use to boost the run-time priority of the thread that requested the I/O operation. |
| [WdfRequestCreate function](nf-wdfrequest-wdfrequestcreate.md) | The WdfRequestCreate method creates an empty framework request object. |
| [WdfRequestCreateFromIrp function](nf-wdfrequest-wdfrequestcreatefromirp.md) | The WdfRequestCreateFromIrp method creates a framework request object from a specified WDM IRP. |
| [WdfRequestFormatRequestUsingCurrentType function](nf-wdfrequest-wdfrequestformatrequestusingcurrenttype.md) | The WdfRequestFormatRequestUsingCurrentType method formats a specified I/O request so that the driver can forward it, unmodified, to the driver's local I/O target. |
| [WdfRequestForwardToIoQueue function](nf-wdfrequest-wdfrequestforwardtoioqueue.md) | The WdfRequestForwardToIoQueue method requeues an I/O request to one of the calling driver's I/O queues. |
| [WdfRequestForwardToParentDeviceIoQueue function](nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue.md) | The WdfRequestForwardToParentDeviceIoQueue method requeues an I/O request from a child device's I/O queue to a specified I/O queue of the child's parent device. |
| [WdfRequestGetCompletionParams function](nf-wdfrequest-wdfrequestgetcompletionparams.md) | The WdfRequestGetCompletionParams method retrieves the I/O completion parameters that are associated with a specified framework request object. |
| [WdfRequestGetEffectiveIoType function](nf-wdfrequest-wdfrequestgeteffectiveiotype.md) | The WdfRequestGetEffectiveIoType method returns the buffer access method that UMDF is using for the data buffers of the specified I/O request. |
| [WdfRequestGetFileObject function](nf-wdfrequest-wdfrequestgetfileobject.md) | The WdfRequestGetFileObject method retrieves the framework file object that is associated with a specified I/O request. |
| [WdfRequestGetInformation function](nf-wdfrequest-wdfrequestgetinformation.md) | The WdfRequestGetInformation method returns completion status information for a specified I/O request. |
| [WdfRequestGetIoQueue function](nf-wdfrequest-wdfrequestgetioqueue.md) | The WdfRequestGetIoQueue method returns a handle to the framework queue object from which a specified I/O request was delivered. |
| [WdfRequestGetParameters function](nf-wdfrequest-wdfrequestgetparameters.md) | The WdfRequestGetParameters method retrieves the parameters that are associated with a specified framework request object. |
| [WdfRequestGetRequestorMode function](nf-wdfrequest-wdfrequestgetrequestormode.md) | The WdfRequestGetRequestorMode method returns the processor access mode of the originator of a specified I/O request. |
| [WdfRequestGetRequestorProcessId function](nf-wdfrequest-wdfrequestgetrequestorprocessid.md) | The WdfRequestGetRequestorProcessId method retrieves the identifier of the process that sent an I/O request. |
| [WdfRequestGetStatus function](nf-wdfrequest-wdfrequestgetstatus.md) | The WdfRequestGetStatus method returns the status of an I/O request. |
| [WdfRequestGetUserModeDriverInitiatedIo function](nf-wdfrequest-wdfrequestgetusermodedriverinitiatedio.md) | The WdfRequestGetUserModeDriverInitiatedIo method determines whether an I/O request is marked as initiated by a UMDF driver. |
| [WdfRequestImpersonate function](nf-wdfrequest-wdfrequestimpersonate.md) | The WdfRequestImpersonate method registers a driver-supplied event callback function that the framework should call for impersonation. |
| [WdfRequestIsCanceled function](nf-wdfrequest-wdfrequestiscanceled.md) | The WdfRequestIsCanceled method determines whether the I/O manager has attempted to cancel a specified I/O request. |
| [WdfRequestIsFrom32BitProcess function](nf-wdfrequest-wdfrequestisfrom32bitprocess.md) | The WdfRequestIsFrom32BitProcess method checks whether the originator of a specified I/O request is a 32-bit user-mode application. |
| [WdfRequestIsFromUserModeDriver function](nf-wdfrequest-wdfrequestisfromusermodedriver.md) | The WdfRequestIsFromUserModeDriver method indicates whether an I/O request came from a user-mode driver or an application. |
| [WdfRequestIsReserved function](nf-wdfrequest-wdfrequestisreserved.md) | The WdfRequestIsReserved method determines whether a specified request object is one that the framework reserved to support guaranteed forward progress during low-memory situations. |
| [WdfRequestMarkCancelable function](nf-wdfrequest-wdfrequestmarkcancelable.md) | The WdfRequestMarkCancelable method enables cancellation of a specified I/O request. |
| [WdfRequestMarkCancelableEx function](nf-wdfrequest-wdfrequestmarkcancelableex.md) | The WdfRequestMarkCancelableEx method enables cancellation of a specified I/O request. |
| [WdfRequestProbeAndLockUserBufferForRead function](nf-wdfrequest-wdfrequestprobeandlockuserbufferforread.md) | The WdfRequestProbeAndLockUserBufferForRead method verifies that an I/O request's user-mode buffer is readable, and then it locks the buffer's physical memory pages so drivers in the driver stack can read the buffer. |
| [WdfRequestProbeAndLockUserBufferForWrite function](nf-wdfrequest-wdfrequestprobeandlockuserbufferforwrite.md) | The WdfRequestProbeAndLockUserBufferForWrite method verifies that an I/O request's user-mode buffer is writeable, and then it locks the buffer's physical memory pages so drivers in the driver stack can write into the buffer. |
| [WdfRequestRequeue function](nf-wdfrequest-wdfrequestrequeue.md) | The WdfRequestRequeue method returns an I/O request to the head of the I/O queue from which it was delivered to the driver. |
| [WdfRequestRetrieveActivityId function](nf-wdfrequest-wdfrequestretrieveactivityid.md) | The WdfRequestRetrieveActivityId method retrieves the current activity identifier associated with an I/O request. |
| [WdfRequestRetrieveInputBuffer function](nf-wdfrequest-wdfrequestretrieveinputbuffer.md) | The WdfRequestRetrieveInputBuffer method retrieves an I/O request's input buffer. |
| [WdfRequestRetrieveInputMemory function](nf-wdfrequest-wdfrequestretrieveinputmemory.md) | The WdfRequestRetrieveInputMemory method retrieves a handle to a framework memory object that represents an I/O request's input buffer. |
| [WdfRequestRetrieveInputWdmMdl function](nf-wdfrequest-wdfrequestretrieveinputwdmmdl.md) | The WdfRequestRetrieveInputWdmMdl method retrieves a memory descriptor list (MDL) that represents an I/O request's input buffer. |
| [WdfRequestRetrieveOutputBuffer function](nf-wdfrequest-wdfrequestretrieveoutputbuffer.md) | The WdfRequestRetrieveOutputBuffer method retrieves an I/O request's output buffer. |
| [WdfRequestRetrieveOutputMemory function](nf-wdfrequest-wdfrequestretrieveoutputmemory.md) | The WdfRequestRetrieveOutputMemory method retrieves a handle to a framework memory object that represents an I/O request's output buffer. |
| [WdfRequestRetrieveOutputWdmMdl function](nf-wdfrequest-wdfrequestretrieveoutputwdmmdl.md) | The WdfRequestRetrieveOutputWdmMdl method retrieves a memory descriptor list (MDL) that represents an I/O request's output buffer. |
| [WdfRequestRetrieveUnsafeUserInputBuffer function](nf-wdfrequest-wdfrequestretrieveunsafeuserinputbuffer.md) | The WdfRequestRetrieveUnsafeUserInputBuffer method retrieves an I/O request's input buffer, if the request's technique for accessing data buffers is neither buffered nor direct I/O. |
| [WdfRequestRetrieveUnsafeUserOutputBuffer function](nf-wdfrequest-wdfrequestretrieveunsafeuseroutputbuffer.md) | The WdfRequestRetrieveUnsafeUserOutputBuffer method retrieves an I/O request's output buffer, if the request's technique for accessing data buffers is neither buffered nor direct I/O. |
| [WdfRequestReuse function](nf-wdfrequest-wdfrequestreuse.md) | The WdfRequestReuse method reinitializes a framework request object so that it can be reused. |
| [WdfRequestSend function](nf-wdfrequest-wdfrequestsend.md) | The WdfRequestSend method sends a specified I/O request to a specified I/O target. |
| [WdfRequestSetActivityId function](nf-wdfrequest-wdfrequestsetactivityid.md) | The WdfRequestSetActivityId method associates an activity identifier with an I/O request. |
| [WdfRequestSetCompletionRoutine function](nf-wdfrequest-wdfrequestsetcompletionroutine.md) | The WdfRequestSetCompletionRoutine method registers or deregisters a completion routine for the specified framework request object. |
| [WdfRequestSetInformation function](nf-wdfrequest-wdfrequestsetinformation.md) | The WdfRequestSetInformation method sets completion status information for a specified I/O request. |
| [WdfRequestSetUserModeDriverInitiatedIo function](nf-wdfrequest-wdfrequestsetusermodedriverinitiatedio.md) | The WdfRequestSetUserModeDriverInitiatedIo method indicates to kernel-mode drivers that sit below the UMDF driver in the same device stack that a particular request should be treated as though it came from a UMDF driver. |
| [WdfRequestStopAcknowledge function](nf-wdfrequest-wdfrequeststopacknowledge.md) | The WdfRequestStopAcknowledge method informs the framework that the driver has stopped processing a specified I/O request. |
| [WdfRequestUnmarkCancelable function](nf-wdfrequest-wdfrequestunmarkcancelable.md) | The WdfRequestUnmarkCancelable method disables cancellation of a specified I/O request. |
| [WdfRequestWdmFormatUsingStackLocation function](nf-wdfrequest-wdfrequestwdmformatusingstacklocation.md) | The WdfRequestWdmFormatUsingStackLocation method formats an I/O request by copying the contents of a specified WDM I/O stack location structure to the next stack location in the request. |
| [WdfRequestWdmGetIrp function](nf-wdfrequest-wdfrequestwdmgetirp.md) | The WdfRequestWdmGetIrp method returns the WDM IRP structure that is associated with a specified framework request object. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_WDF_REQUEST_CANCEL callback](nc-wdfrequest-evt_wdf_request_cancel.md) | A driver's EvtRequestCancel event callback function handles operations that must be performed when an I/O request is canceled. |
| [EVT_WDF_REQUEST_COMPLETION_ROUTINE callback](nc-wdfrequest-evt_wdf_request_completion_routine.md) | A driver's CompletionRoutine event callback function executes when another driver completes a specified I/O request. |
| [EVT_WDF_REQUEST_IMPERSONATE callback](nc-wdfrequest-evt_wdf_request_impersonate.md) | A driver's EvtRequestImpersonate event callback function performs tasks at the requested impersonation level, such as opening a protected file. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_REQUEST_COMPLETION_PARAMS structure](ns-wdfrequest-_wdf_request_completion_params.md) | The WDF_REQUEST_COMPLETION_PARAMS structure contains parameters that are associated with the completion of an I/O request. |
| [_WDF_REQUEST_FORWARD_OPTIONS structure](ns-wdfrequest-_wdf_request_forward_options.md) | The WDF_REQUEST_FORWARD_OPTIONS structure contains options for requeuing an I/O request from a child device's I/O queue to the parent device's I/O queue. |
| [_WDF_REQUEST_PARAMETERS structure](ns-wdfrequest-_wdf_request_parameters.md) | The WDF_REQUEST_PARAMETERS structure receives parameters that are associated with an I/O request. |
| [_WDF_REQUEST_REUSE_PARAMS structure](ns-wdfrequest-_wdf_request_reuse_params.md) | The WDF_REQUEST_REUSE_PARAMS structure specifies information that is associated with a reused I/O request. |
| [_WDF_REQUEST_SEND_OPTIONS structure](ns-wdfrequest-_wdf_request_send_options.md) | The WDF_REQUEST_SEND_OPTIONS structure specifies options that are associated with sending an I/O request to an I/O target. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WDF_REQUEST_FORWARD_OPTIONS_FLAGS enumeration](ne-wdfrequest-_wdf_request_forward_options_flags.md) | The WDF_REQUEST_FORWARD_OPTIONS_FLAGS enumeration type defines flags that are used in a driver's WDF_REQUEST_FORWARD_OPTIONS structure. |
| [_WDF_REQUEST_REUSE_FLAGS enumeration](ne-wdfrequest-_wdf_request_reuse_flags.md) | The WDF_REQUEST_REUSE_FLAGS enumeration type defines flags that are used in a driver's WDF_REQUEST_REUSE_PARAMS structure. |
| [_WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration](ne-wdfrequest-_wdf_request_send_options_flags.md) | The WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration type defines flags that are used in a driver's WDF_REQUEST_SEND_OPTIONS structure. |
| [_WDF_REQUEST_STOP_ACTION_FLAGS enumeration](ne-wdfrequest-_wdf_request_stop_action_flags.md) | The WDF_REQUEST_STOP_ACTION_FLAGS enumeration type defines flags that the framework passes to a driver's EvtIoStop callback function. |
| [_WDF_REQUEST_TYPE enumeration](ne-wdfrequest-_wdf_request_type.md) | The WDF_REQUEST_TYPE enumeration type identifies types of requests that a framework request object might contain. |
