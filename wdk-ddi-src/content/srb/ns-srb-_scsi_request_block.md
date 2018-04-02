---
UID: NS:srb._SCSI_REQUEST_BLOCK
title: "_SCSI_REQUEST_BLOCK"
author: windows-driver-content
description: SCSI_REQUEST_BLOCK structure
old-location: storage\scsi_request_block.htm
old-project: storage
ms.assetid: ddd5180d-275c-4226-9af8-8e2ae25256e7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSCSI_REQUEST_BLOCK, PSCSI_REQUEST_BLOCK, PSCSI_REQUEST_BLOCK structure pointer [Storage Devices], SCSI_REQUEST_BLOCK, SCSI_REQUEST_BLOCK structure [Storage Devices], SRB_FLAGS_ALLOCATED_FROM_ZONE, SRB_FLAGS_BYPASS_FROZEN_QUEUE, SRB_FLAGS_BYPASS_LOCKED_QUEUE, SRB_FLAGS_DATA_IN, SRB_FLAGS_DATA_OUT, SRB_FLAGS_DISABLE_AUTOSENSE, SRB_FLAGS_DISABLE_DISCONNECT, SRB_FLAGS_DISABLE_SYNCH_TRANSFER, SRB_FLAGS_FREE_SENSE_BUFFER, SRB_FLAGS_IS_ACTIVE, SRB_FLAGS_NO_DATA_TRANSFER, SRB_FLAGS_NO_KEEP_AWAKE, SRB_FLAGS_NO_QUEUE_FREEZE, SRB_FLAGS_QUEUE_ACTION_ENABLE, SRB_FLAGS_SGLIST_FROM_POOL, SRB_FLAGS_UNSPECIFIED_DIRECTION, SRB_FUNCTION_ABORT_COMMAND, SRB_FUNCTION_DUMP_POINTERS, SRB_FUNCTION_EXECUTE_SCSI, SRB_FUNCTION_FLUSH, SRB_FUNCTION_FREE_DUMP_POINTERS, SRB_FUNCTION_IO_CONTROL, SRB_FUNCTION_LOCK_QUEUE, SRB_FUNCTION_RECEIVE_EVENT, SRB_FUNCTION_RELEASE_RECOVERY, SRB_FUNCTION_RESET_BUS, SRB_FUNCTION_RESET_DEVICE, SRB_FUNCTION_RESET_LOGICAL_UNIT, SRB_FUNCTION_SHUTDOWN, SRB_FUNCTION_TERMINATE_IO, SRB_FUNCTION_UNLOCK_QUEUE, SRB_STATUS_ABORTED, SRB_STATUS_ABORT_FAILED, SRB_STATUS_AUTOSENSE_VALID, SRB_STATUS_BAD_FUNCTION, SRB_STATUS_BUSY, SRB_STATUS_BUS_RESET, SRB_STATUS_COMMAND_TIMEOUT, SRB_STATUS_DATA_OVERRUN, SRB_STATUS_ERROR, SRB_STATUS_ERROR_RECOVERY, SRB_STATUS_INTERNAL_ERROR, SRB_STATUS_INVALID_LUN, SRB_STATUS_INVALID_PATH_ID, SRB_STATUS_INVALID_REQUEST, SRB_STATUS_INVALID_TARGET_ID, SRB_STATUS_MESSAGE_REJECTED, SRB_STATUS_NO_DEVICE, SRB_STATUS_NO_HBA, SRB_STATUS_PARITY_ERROR, SRB_STATUS_PENDING, SRB_STATUS_PHASE_SEQUENCE_FAILURE, SRB_STATUS_QUEUE_FROZEN, SRB_STATUS_REQUEST_FLUSHED, SRB_STATUS_REQUEST_SENSE_FAILED, SRB_STATUS_SELECTION_TIMEOUT, SRB_STATUS_SUCCESS, SRB_STATUS_TIMEOUT, SRB_STATUS_UNEXPECTED_BUS_FREE, _SCSI_REQUEST_BLOCK, srb/PSCSI_REQUEST_BLOCK, srb/SCSI_REQUEST_BLOCK, storage.scsi_request_block, structs-scsibus_9cd58a74-3ae0-4536-ac0c-efaf73bf9733.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: srb.h
req.include-header: Srb.h, Minitape.h, Storport.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	srb.h
api_name:
-	SCSI_REQUEST_BLOCK
product: Windows
targetos: Windows
req.typenames: SCSI_REQUEST_BLOCK, *PSCSI_REQUEST_BLOCK
req.product: Windows 10 or later.
---

# _SCSI_REQUEST_BLOCK structure


## -description


<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Length

Specifies the size in bytes of this structure.


### -field Function

Specifies the operation to be performed, which can be one of the following values:



#### SRB_FUNCTION_EXECUTE_SCSI (0x00)

A SCSI device I/O request should be executed on the target logical unit.



#### SRB_FUNCTION_ABORT_COMMAND (0x10)

A SCSIMESS_ABORT message should be sent to cancel the request pointed to by the <b>NextSrb</b> member. If this is a tagged-queue request, a SCSIMESS_ABORT_WITH_TAG message should be used instead. If the indicated request has been completed, this request should be completed normally. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b>, <b>Lun</b>, and <b>NextSrb</b> members are valid.



#### SRB_FUNCTION_RESET_DEVICE (0x13)

The ScsiPort driver no longer sends this SRB to its miniports. Only Storport miniport drivers use this SRB. The SCSI target controller should be reset using the SCSIMESS_BUS_DEVICE_RESET message. The miniport driver should complete any active requests for the target controller. Only the SRB <b>Function</b>, <b>TargetId</b>, and <b>PathId</b> members are valid.



#### SRB_FUNCTION_RESET_LOGICAL_UNIT (0x20)

The logical unit should be reset, if possible. The HBA miniport driver should complete any active requests for the logical unit. Only the <b>Function</b>, <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b> members of the SRB are valid. Storport supports this type of reset, but SCSI port does not. 



#### SRB_FUNCTION_RESET_BUS (0x12)

The SCSI bus should be reset using the SCSIMESS_BUS_DEVICE_RESET message. A miniport driver receives this request only if a given request has timed out and a subsequent request to abort the timed-out request also has timed out. Only the SRB <b>Function</b> and <b>PathId</b> members are valid.



#### SRB_FUNCTION_TERMINATE_IO (0x14)

A SCSIMESS_TERMINATE_IO_PROCESS message should be sent to cancel the request pointed to by the <b>NextSrb</b> member. If the indicated request has already completed, this request should be completed normally. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b>, <b>Lun</b>, and <b>NextSrb</b> members are valid.



#### SRB_FUNCTION_RELEASE_RECOVERY (0x11)

A SCSIMESS_RELEASE_RECOVERY message should be sent to the target controller. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b> members are valid.



#### SRB_FUNCTION_RECEIVE_EVENT (0x03)

The HBA should be prepared to receive an asynchronous event notification from the addressed target. The SRB <b>DataBuffer</b> member indicates where the data should be placed.



#### SRB_FUNCTION_SHUTDOWN (0x07)

The system is being shut down. This request is sent to a miniport driver only if it set <b>CachesData</b> to <b>TRUE</b> in the PORT_CONFIGURATION_INFORMATION for the HBA. Such a miniport driver can receive several of these notifications before all system activity actually stops. However, the last shutdown notification will occur after the last start I/O. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b> and <b>Lun</b> members are valid.



#### SRB_FUNCTION_FLUSH (0x08)

The miniport driver should flush any cached data for the target device. This request is sent to the miniport driver only if it set <b>CachesData</b> to <b>TRUE</b> in the PORT_CONFIGURATION_INFORMATION for the HBA. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b> and <b>Lun</b> members are valid.



#### SRB_FUNCTION_IO_CONTROL (0x02)

The request is an I/O control request, originating in a user-mode application with a dedicated HBA. The SRB <b>DataBuffer</b> points to an SRB_IO_CONTROL header followed by the data area. The value in <b>DataBuffer</b> can be used by the driver, regardless of the value of <b>MapBuffers</b>. Only the SRB <b>Function</b>, <b>SrbFlags</b>, <b>TimeOutValue</b>, <b>DataBuffer</b>, and <b>DataTransferLength</b> members are valid, along with the <b>SrbExtension</b> member if the miniport driver requested SRB extensions when it initialized. If a miniport driver controls an application-dedicated HBA so it supports this request, the miniport driver should execute the request and notify the OS-specific port driver when the SRB has completed, using the normal mechanism of calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564657">ScsiPortNotification</a> with <b>RequestComplete</b> and <b>NextRequest</b>.



#### SRB_FUNCTION_LOCK_QUEUE (0x18)

Holds requests queued by the port driver for a particular logical unit, typically while a power request is being processed. Only the SRB <b>Length</b>, <b>Function</b>, <b>SrbFlags</b>, and <b>OriginalRequest</b> members are valid. When the queue is locked, only requests with <b>SrbFlags</b> ORed with SRB_FLAGS_BYPASS_LOCKED_QUEUE will be processed. SCSI miniport drivers do not process SRB_FUNCTION_LOCK_QUEUE requests. 



#### SRB_FUNCTION_UNLOCK_QUEUE (0x19)

Releases the port driver's queue for a logical unit that was previously locked with SRB_FUNCTION_LOCK_QUEUE. The <b>SrbFlags</b> of the unlock request must be ORed with SRB_FLAGS_BYPASS_LOCKED_QUEUE. Only the SRB <b>Length</b>, <b>Function</b>, <b>SrbFlags</b>, and <b>OriginalRequest</b> members are valid. SCSI miniport drivers do not process SRB_FUNCTION_UNLOCK_QUEUE requests.



#### SRB_FUNCTION_DUMP_POINTERS (0x26)

A request with this function is sent to a Storport miniport driver that is used to control the disk that holds the crash dump data. The request collects information needed from the miniport driver to support crash dump and hibernation. See the <b>MINIPORT_DUMP_POINTERS</b> structure. A physical miniport driver must set the STOR_FEATURE_DUMP_POINTERS flag in the <b>FeatureSupport</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a> to receive a request with this function.



#### SRB_FUNCTION_FREE_DUMP_POINTERS (0x27)

A request with this function is sent to a Storport miniport driver to release any resources allocated during a previous request for SRB_FUNCTION_DUMP_POINTERS.


### -field SrbStatus

Returns the status of the completed request. This member should be set by the miniport driver before it notifies the OS-specific driver that the request has completed by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff564657">ScsiPortNotification</a> with <b>RequestComplete</b>. The value of this member can be one of the following:



#### SRB_STATUS_PENDING

Indicates the request is in progress. The OS-specific port driver initializes <b>SrbStatus</b> to this value.



#### SRB_STATUS_SUCCESS

Indicates the request was completed successfully.



#### SRB_STATUS_ABORTED

Indicates the request was aborted as directed by the port driver. A miniport driver sets this status in the <b>NextSrb</b> for a successful SRB_FUNCTION_ABORT_COMMAND request.



#### SRB_STATUS_ABORT_FAILED

Indicates an attempt to abort the request failed. Return this status for an SRB_FUNCTION_ABORT_COMMAND request when the specified request cannot be located.



#### SRB_STATUS_ERROR

Indicates the request was completed with an error in the SCSI bus status.



#### SRB_STATUS_BUSY

Indicates the miniport driver or target device could not accept the request at this time. The OS-specific port driver will resubmit the request later.



#### SRB_STATUS_INTERNAL_ERROR

Indicates that the SCSI Port driver could not deliver the request to the miniport driver or target device. In such cases, status is recorded in <b>InternalStatus</b>.



#### SRB_STATUS_INVALID_REQUEST

Indicates the miniport driver does not support the given request.



#### SRB_STATUS_NO_DEVICE

Indicates the device did not respond.



#### SRB_STATUS_TIMEOUT

Indicates the request timed out.



#### SRB_STATUS_SELECTION_TIMEOUT

Indicates the SCSI device selection timed out.



#### SRB_STATUS_COMMAND_TIMEOUT

Indicates the target did not complete the command within the time limit.



#### SRB_STATUS_MESSAGE_REJECTED

Indicates the target rejected a message. This is normally returned only for such message-type requests as SRB_FUNCTION_TERMINATE_IO.



#### SRB_STATUS_BUS_RESET

Indicates a bus reset occurred while this request was being executed.



#### SRB_STATUS_PARITY_ERROR

Indicates a parity error occurred on the SCSI bus and that a retry failed.



#### SRB_STATUS_REQUEST_SENSE_FAILED

Indicates the request-sense command failed. This is returned only if the HBA performs auto request sense and the miniport driver set <b>AutoRequestSense</b> to <b>TRUE</b> in the PORT_CONFIGURATION_INFORMATION for this HBA.



#### SRB_STATUS_NO_HBA

Indicates the HBA does not respond.



#### SRB_STATUS_DATA_OVERRUN

Indicates that a data overrun or underrun error occurred. The miniport driver also must update the SRB's <b>DataTransferLength</b> member to indicate how much data actually was transferred if an underrun occurs. 



#### SRB_STATUS_UNEXPECTED_BUS_FREE

Indicates the target disconnected unexpectedly.



#### SRB_STATUS_PHASE_SEQUENCE_FAILURE

Indicates the HBA detected an illegal phase sequence failure error.



#### SRB_STATUS_REQUEST_FLUSHED

Indicates the request for status was stopped.



#### SRB_STATUS_BAD_FUNCTION

Indicates the SRB <b>Function</b> code is not supported.



#### SRB_STATUS_INVALID_PATH_ID

Indicates the <b>PathId</b> specified in the SRB does not exist.



#### SRB_STATUS_INVALID_TARGET_ID

Indicates the <b>TargetID</b> value in the SRB is invalid.



#### SRB_STATUS_INVALID_LUN

Indicates the <b>Lun</b> value in the SRB is invalid.



#### SRB_STATUS_ERROR_RECOVERY

Indicates the request was completed with an error in the SCSI bus status and that the SCSI INITIATE RECOVERY message was received.



#### SRB_STATUS_AUTOSENSE_VALID

Indicates information returned in the <b>SenseInfoBuffer</b> is valid.



#### SRB_STATUS_QUEUE_FROZEN

A miniport driver should <i>never</i> set the <b>SrbStatus</b> member to this value. The Windows port driver can set this value to inform a storage class driver that its queue of requests for a particular peripheral has been frozen. 


### -field ScsiStatus

Returns the SCSI status that was returned by the HBA or target device. If the status is not SUCCESS, the miniport driver should set the <b>SrbStatus</b> member to SRB_STATUS_ERROR.


### -field PathId

Indicates the SCSI port or bus for the request. This value is zero-based.


### -field TargetId

Indicates the target controller or device on the bus.


### -field Lun

Indicates the logical unit number of the device.


### -field QueueTag

Contains the queue-tag value assigned by the OS-specific port driver. If this member is used for tagged queuing, the HBA supports internal queuing of requests to LUs and the miniport driver set <b>TaggedQueueing</b> to <b>TRUE</b> in the PORT_CONFIGURATION_INFORMATION for this HBA.


### -field QueueAction

Indicates the tagged-queuing message to be used when the SRB_FLAGS_QUEUE_ACTION_ENABLE flag is set. The value can be one of the following: SRB_SIMPLE_TAG_REQUEST, SRB_HEAD_OF_QUEUE_TAG_REQUEST, or SRB_ORDERED_QUEUE_TAG_REQUEST, as defined according to the SCSI specification.


### -field CdbLength

Indicates the size in bytes of the SCSI-2 or later command descriptor block.


### -field SenseInfoBufferLength

Indicates the size in bytes of the request-sense buffer. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred.


### -field SrbFlags

Indicates various parameters and options about the request. <b>SrbFlags</b> is read-only, except when SRB_FLAGS_UNSPECIFIED_DIRECTION is set and miniport drivers of subordinate DMA adapters are required to update SRB_FLAGS_DATA_IN or SRB_FLAGS_DATA_OUT. This member can have one or more of the following flags set:



#### SRB_FLAGS_QUEUE_ACTION_ENABLE

Indicates tagged-queue actions are to be enabled.



#### SRB_FLAGS_DISABLE_AUTOSENSE

Indicates that request-sense information should not be returned.



#### SRB_FLAGS_DATA_IN

Indicates data will be transferred from the device to the system.



#### SRB_FLAGS_DATA_OUT

Indicates data will be transferred from the system to the device.



#### SRB_FLAGS_UNSPECIFIED_DIRECTION

Defined for backward compatibility with the ASPI/CAM SCSI interfaces, this flag indicates that the transfer direction could be either of the preceding because both of the preceding flags are set. If this flag is set, a miniport driver should determine the transfer direction by examining the data phase for the target on the SCSI bus. If its HBA is a subordinate DMA device, such a miniport driver must update SRB_FLAGS_DATA_OUT or SRB_FLAGS_DATA_IN to the correct value before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff564649">ScsiPortIoMapTransfer</a>.



#### SRB_FLAGS_NO_DATA_TRANSFER

Indicates no data transfer with this request. If this is set, the flags SRB_FLAGS_DATA_OUT, SRB_FLAGS_DATA_IN, and SRB_FLAGS_UNSPECIFIED_DIRECTION are clear.



#### SRB_FLAGS_DISABLE_SYNCH_TRANSFER

Indicates the HBA, if possible, should perform asynchronous I/O for this transfer request. If synchronous I/O was negotiated previously, the HBA must renegotiate for asynchronous I/O before performing the transfer.



#### SRB_FLAGS_DISABLE_DISCONNECT

Indicates the HBA should not allow the target to disconnect from the SCSI bus during processing of this request.



#### SRB_FLAGS_BYPASS_FROZEN_QUEUE

Is irrelevant to miniport drivers.



#### SRB_FLAGS_NO_QUEUE_FREEZE

Is irrelevant to miniport drivers.



#### SRB_FLAGS_IS_ACTIVE

Is irrelevant to miniport drivers.



#### SRB_FLAGS_ALLOCATED_FROM_ZONE

Is irrelevant to miniport drivers and is obsolete to current Windows class drivers. To a Windows legacy class driver, this indicates whether the SRB was allocated from a zone buffer. If this flag is set, the class driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545387">ExInterlockedFreeToZone</a> to release the SRB; otherwise, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>. New class drivers should use lookaside lists rather than zone buffers.



#### SRB_FLAGS_SGLIST_FROM_POOL

Is irrelevant to miniport drivers. To a Windows class driver, this indicates that memory for a scatter/gather list was allocated from nonpaged pool. If this flag is set, the class driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a> to release the memory after the SRB is completed. 



#### SRB_FLAGS_BYPASS_LOCKED_QUEUE

Is irrelevant to miniport drivers. To the port driver, this flag indicates that the request should be processed whether the logical-unit queue is locked. A higher-level driver must set this flag to send an SRB_FUNCTION_UNLOCK_QUEUE request.



#### SRB_FLAGS_NO_KEEP_AWAKE

Is irrelevant to miniport drivers. A Windows  class driver uses this flag to indicate to the port driver to report idle rather than powering up the device to handle this request.



#### SRB_FLAGS_FREE_SENSE_BUFFER

Indicates that either the port or the miniport driver has allocated a buffer for sense data. This informs the class driver that it must free the sense data buffer after extracting the data.


### -field DataTransferLength

Indicates the size in bytes of the data buffer. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred.


### -field TimeOutValue

Indicates the interval in seconds that the request can execute before the OS-specific port driver might consider it timed out. Miniport drivers are not required to time requests because the port driver already does.


### -field DataBuffer

Points to the data buffer. Miniport drivers should not use this value as a data pointer unless the miniport driver set <b>MapBuffers</b> to <b>TRUE</b> in the PORT_CONFIGURATION_INFORMATION for the HBA. In the case of SRB_FUNCTION_IO_CONTROL requests, however, miniport drivers can use this value as a data pointer regardless of the value of <b>MapBuffers</b>.


### -field SenseInfoBuffer

Points to the request-sense buffer. A miniport driver is not required to provide request-sense data after a CHECK CONDITION. 


### -field NextSrb

Indicates the SCSI_REQUEST_BLOCK to which this request applies. Only a small subset of requests use a second SRB, for example SRB_FUNCTION_ABORT_COMMAND.


### -field OriginalRequest

Points to the IRP for this request. This member is irrelevant to miniport drivers


### -field SrbExtension

Points to the Srb extension. A miniport driver must not use this member if it set <b>SrbExtensionSize</b> to zero in the SCSI_HW_INITIALIZATION_DATA. The memory at <b>SrbExtension</b> is not initialized by the OS-specific port driver, and the miniport driver-determined data can be accessed directly by the HBA. The corresponding physical address can be obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff564636">ScsiPortGetPhysicalAddress</a> with the <b>SrbExtension</b> pointer.


### -field Reserved

Reserved.


### -field Cdb

Specifies the SCSI-2 or later command descriptor block to be sent to the target device. 


##### - Function.SRB_FUNCTION_ABORT_COMMAND (0x10)

A SCSIMESS_ABORT message should be sent to cancel the request pointed to by the <b>NextSrb</b> member. If this is a tagged-queue request, a SCSIMESS_ABORT_WITH_TAG message should be used instead. If the indicated request has been completed, this request should be completed normally. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b>, <b>Lun</b>, and <b>NextSrb</b> members are valid.


##### - Function.SRB_FUNCTION_DUMP_POINTERS (0x26)

A request with this function is sent to a Storport miniport driver that is used to control the disk that holds the crash dump data. The request collects information needed from the miniport driver to support crash dump and hibernation. See the <b>MINIPORT_DUMP_POINTERS</b> structure. A physical miniport driver must set the STOR_FEATURE_DUMP_POINTERS flag in the <b>FeatureSupport</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a> to receive a request with this function.


##### - Function.SRB_FUNCTION_EXECUTE_SCSI (0x00)

A SCSI device I/O request should be executed on the target logical unit.


##### - Function.SRB_FUNCTION_FLUSH (0x08)

The miniport driver should flush any cached data for the target device. This request is sent to the miniport driver only if it set <b>CachesData</b> to <b>TRUE</b> in the PORT_CONFIGURATION_INFORMATION for the HBA. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b> and <b>Lun</b> members are valid.


##### - Function.SRB_FUNCTION_FREE_DUMP_POINTERS (0x27)

A request with this function is sent to a Storport miniport driver to release any resources allocated during a previous request for SRB_FUNCTION_DUMP_POINTERS.


##### - Function.SRB_FUNCTION_IO_CONTROL (0x02)

The request is an I/O control request, originating in a user-mode application with a dedicated HBA. The SRB <b>DataBuffer</b> points to an SRB_IO_CONTROL header followed by the data area. The value in <b>DataBuffer</b> can be used by the driver, regardless of the value of <b>MapBuffers</b>. Only the SRB <b>Function</b>, <b>SrbFlags</b>, <b>TimeOutValue</b>, <b>DataBuffer</b>, and <b>DataTransferLength</b> members are valid, along with the <b>SrbExtension</b> member if the miniport driver requested SRB extensions when it initialized. If a miniport driver controls an application-dedicated HBA so it supports this request, the miniport driver should execute the request and notify the OS-specific port driver when the SRB has completed, using the normal mechanism of calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564657">ScsiPortNotification</a> with <b>RequestComplete</b> and <b>NextRequest</b>.


##### - Function.SRB_FUNCTION_LOCK_QUEUE (0x18)

Holds requests queued by the port driver for a particular logical unit, typically while a power request is being processed. Only the SRB <b>Length</b>, <b>Function</b>, <b>SrbFlags</b>, and <b>OriginalRequest</b> members are valid. When the queue is locked, only requests with <b>SrbFlags</b> ORed with SRB_FLAGS_BYPASS_LOCKED_QUEUE will be processed. SCSI miniport drivers do not process SRB_FUNCTION_LOCK_QUEUE requests. 


##### - Function.SRB_FUNCTION_RECEIVE_EVENT (0x03)

The HBA should be prepared to receive an asynchronous event notification from the addressed target. The SRB <b>DataBuffer</b> member indicates where the data should be placed.


##### - Function.SRB_FUNCTION_RELEASE_RECOVERY (0x11)

A SCSIMESS_RELEASE_RECOVERY message should be sent to the target controller. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b> members are valid.


##### - Function.SRB_FUNCTION_RESET_BUS (0x12)

The SCSI bus should be reset using the SCSIMESS_BUS_DEVICE_RESET message. A miniport driver receives this request only if a given request has timed out and a subsequent request to abort the timed-out request also has timed out. Only the SRB <b>Function</b> and <b>PathId</b> members are valid.


##### - Function.SRB_FUNCTION_RESET_DEVICE (0x13)

The ScsiPort driver no longer sends this SRB to its miniports. Only Storport miniport drivers use this SRB. The SCSI target controller should be reset using the SCSIMESS_BUS_DEVICE_RESET message. The miniport driver should complete any active requests for the target controller. Only the SRB <b>Function</b>, <b>TargetId</b>, and <b>PathId</b> members are valid.


##### - Function.SRB_FUNCTION_RESET_LOGICAL_UNIT (0x20)

The logical unit should be reset, if possible. The HBA miniport driver should complete any active requests for the logical unit. Only the <b>Function</b>, <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b> members of the SRB are valid. Storport supports this type of reset, but SCSI port does not. 


##### - Function.SRB_FUNCTION_SHUTDOWN (0x07)

The system is being shut down. This request is sent to a miniport driver only if it set <b>CachesData</b> to <b>TRUE</b> in the PORT_CONFIGURATION_INFORMATION for the HBA. Such a miniport driver can receive several of these notifications before all system activity actually stops. However, the last shutdown notification will occur after the last start I/O. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b> and <b>Lun</b> members are valid.


##### - Function.SRB_FUNCTION_TERMINATE_IO (0x14)

A SCSIMESS_TERMINATE_IO_PROCESS message should be sent to cancel the request pointed to by the <b>NextSrb</b> member. If the indicated request has already completed, this request should be completed normally. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b>, <b>Lun</b>, and <b>NextSrb</b> members are valid.


##### - Function.SRB_FUNCTION_UNLOCK_QUEUE (0x19)

Releases the port driver's queue for a logical unit that was previously locked with SRB_FUNCTION_LOCK_QUEUE. The <b>SrbFlags</b> of the unlock request must be ORed with SRB_FLAGS_BYPASS_LOCKED_QUEUE. Only the SRB <b>Length</b>, <b>Function</b>, <b>SrbFlags</b>, and <b>OriginalRequest</b> members are valid. SCSI miniport drivers do not process SRB_FUNCTION_UNLOCK_QUEUE requests.


#### - InternalStatus

Used by the SCSI Port driver, instead of <b>SrbStatus</b>, to report the status of the completed request whenever the request cannot be delivered to the miniport driver. In such cases, <b>SrbStatus</b> is set to SRB_STATUS_INTERNAL_ERROR. This member is used exclusively for communication between the SCSI Port and the class driver and should not be used by miniport drivers.


#### - LinkTimeoutValue



#### offset 2c



#### 


##### - LinkTimeoutValue.


##### - LinkTimeoutValue.offset 2c


#### - QueueSortKey

Specifies the offset from the start of the media or zero, depending on the type of the target device. 


##### - SrbFlags.SRB_FLAGS_ALLOCATED_FROM_ZONE

Is irrelevant to miniport drivers and is obsolete to current Windows class drivers. To a Windows legacy class driver, this indicates whether the SRB was allocated from a zone buffer. If this flag is set, the class driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545387">ExInterlockedFreeToZone</a> to release the SRB; otherwise, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>. New class drivers should use lookaside lists rather than zone buffers.


##### - SrbFlags.SRB_FLAGS_BYPASS_FROZEN_QUEUE

Is irrelevant to miniport drivers.


##### - SrbFlags.SRB_FLAGS_BYPASS_LOCKED_QUEUE

Is irrelevant to miniport drivers. To the port driver, this flag indicates that the request should be processed whether the logical-unit queue is locked. A higher-level driver must set this flag to send an SRB_FUNCTION_UNLOCK_QUEUE request.


##### - SrbFlags.SRB_FLAGS_DATA_IN

Indicates data will be transferred from the device to the system.


##### - SrbFlags.SRB_FLAGS_DATA_OUT

Indicates data will be transferred from the system to the device.


##### - SrbFlags.SRB_FLAGS_DISABLE_AUTOSENSE

Indicates that request-sense information should not be returned.


##### - SrbFlags.SRB_FLAGS_DISABLE_DISCONNECT

Indicates the HBA should not allow the target to disconnect from the SCSI bus during processing of this request.


##### - SrbFlags.SRB_FLAGS_DISABLE_SYNCH_TRANSFER

Indicates the HBA, if possible, should perform asynchronous I/O for this transfer request. If synchronous I/O was negotiated previously, the HBA must renegotiate for asynchronous I/O before performing the transfer.


##### - SrbFlags.SRB_FLAGS_FREE_SENSE_BUFFER

Indicates that either the port or the miniport driver has allocated a buffer for sense data. This informs the class driver that it must free the sense data buffer after extracting the data.


##### - SrbFlags.SRB_FLAGS_IS_ACTIVE

Is irrelevant to miniport drivers.


##### - SrbFlags.SRB_FLAGS_NO_DATA_TRANSFER

Indicates no data transfer with this request. If this is set, the flags SRB_FLAGS_DATA_OUT, SRB_FLAGS_DATA_IN, and SRB_FLAGS_UNSPECIFIED_DIRECTION are clear.


##### - SrbFlags.SRB_FLAGS_NO_KEEP_AWAKE

Is irrelevant to miniport drivers. A Windows  class driver uses this flag to indicate to the port driver to report idle rather than powering up the device to handle this request.


##### - SrbFlags.SRB_FLAGS_NO_QUEUE_FREEZE

Is irrelevant to miniport drivers.


##### - SrbFlags.SRB_FLAGS_QUEUE_ACTION_ENABLE

Indicates tagged-queue actions are to be enabled.


##### - SrbFlags.SRB_FLAGS_SGLIST_FROM_POOL

Is irrelevant to miniport drivers. To a Windows class driver, this indicates that memory for a scatter/gather list was allocated from nonpaged pool. If this flag is set, the class driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a> to release the memory after the SRB is completed. 


##### - SrbFlags.SRB_FLAGS_UNSPECIFIED_DIRECTION

Defined for backward compatibility with the ASPI/CAM SCSI interfaces, this flag indicates that the transfer direction could be either of the preceding because both of the preceding flags are set. If this flag is set, a miniport driver should determine the transfer direction by examining the data phase for the target on the SCSI bus. If its HBA is a subordinate DMA device, such a miniport driver must update SRB_FLAGS_DATA_OUT or SRB_FLAGS_DATA_IN to the correct value before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff564649">ScsiPortIoMapTransfer</a>.


##### - SrbStatus.SRB_STATUS_ABORTED

Indicates the request was aborted as directed by the port driver. A miniport driver sets this status in the <b>NextSrb</b> for a successful SRB_FUNCTION_ABORT_COMMAND request.


##### - SrbStatus.SRB_STATUS_ABORT_FAILED

Indicates an attempt to abort the request failed. Return this status for an SRB_FUNCTION_ABORT_COMMAND request when the specified request cannot be located.


##### - SrbStatus.SRB_STATUS_AUTOSENSE_VALID

Indicates information returned in the <b>SenseInfoBuffer</b> is valid.


##### - SrbStatus.SRB_STATUS_BAD_FUNCTION

Indicates the SRB <b>Function</b> code is not supported.


##### - SrbStatus.SRB_STATUS_BUSY

Indicates the miniport driver or target device could not accept the request at this time. The OS-specific port driver will resubmit the request later.


##### - SrbStatus.SRB_STATUS_BUS_RESET

Indicates a bus reset occurred while this request was being executed.


##### - SrbStatus.SRB_STATUS_COMMAND_TIMEOUT

Indicates the target did not complete the command within the time limit.


##### - SrbStatus.SRB_STATUS_DATA_OVERRUN

Indicates that a data overrun or underrun error occurred. The miniport driver also must update the SRB's <b>DataTransferLength</b> member to indicate how much data actually was transferred if an underrun occurs. 


##### - SrbStatus.SRB_STATUS_ERROR

Indicates the request was completed with an error in the SCSI bus status.


##### - SrbStatus.SRB_STATUS_ERROR_RECOVERY

Indicates the request was completed with an error in the SCSI bus status and that the SCSI INITIATE RECOVERY message was received.


##### - SrbStatus.SRB_STATUS_INTERNAL_ERROR

Indicates that the SCSI Port driver could not deliver the request to the miniport driver or target device. In such cases, status is recorded in <b>InternalStatus</b>.


##### - SrbStatus.SRB_STATUS_INVALID_LUN

Indicates the <b>Lun</b> value in the SRB is invalid.


##### - SrbStatus.SRB_STATUS_INVALID_PATH_ID

Indicates the <b>PathId</b> specified in the SRB does not exist.


##### - SrbStatus.SRB_STATUS_INVALID_REQUEST

Indicates the miniport driver does not support the given request.


##### - SrbStatus.SRB_STATUS_INVALID_TARGET_ID

Indicates the <b>TargetID</b> value in the SRB is invalid.


##### - SrbStatus.SRB_STATUS_MESSAGE_REJECTED

Indicates the target rejected a message. This is normally returned only for such message-type requests as SRB_FUNCTION_TERMINATE_IO.


##### - SrbStatus.SRB_STATUS_NO_DEVICE

Indicates the device did not respond.


##### - SrbStatus.SRB_STATUS_NO_HBA

Indicates the HBA does not respond.


##### - SrbStatus.SRB_STATUS_PARITY_ERROR

Indicates a parity error occurred on the SCSI bus and that a retry failed.


##### - SrbStatus.SRB_STATUS_PENDING

Indicates the request is in progress. The OS-specific port driver initializes <b>SrbStatus</b> to this value.


##### - SrbStatus.SRB_STATUS_PHASE_SEQUENCE_FAILURE

Indicates the HBA detected an illegal phase sequence failure error.


##### - SrbStatus.SRB_STATUS_QUEUE_FROZEN

A miniport driver should <i>never</i> set the <b>SrbStatus</b> member to this value. The Windows port driver can set this value to inform a storage class driver that its queue of requests for a particular peripheral has been frozen. 


##### - SrbStatus.SRB_STATUS_REQUEST_FLUSHED

Indicates the request for status was stopped.


##### - SrbStatus.SRB_STATUS_REQUEST_SENSE_FAILED

Indicates the request-sense command failed. This is returned only if the HBA performs auto request sense and the miniport driver set <b>AutoRequestSense</b> to <b>TRUE</b> in the PORT_CONFIGURATION_INFORMATION for this HBA.


##### - SrbStatus.SRB_STATUS_SELECTION_TIMEOUT

Indicates the SCSI device selection timed out.


##### - SrbStatus.SRB_STATUS_SUCCESS

Indicates the request was completed successfully.


##### - SrbStatus.SRB_STATUS_TIMEOUT

Indicates the request timed out.


##### - SrbStatus.SRB_STATUS_UNEXPECTED_BUS_FREE

Indicates the target disconnected unexpectedly.


## -remarks



Windows storage class and filter drivers can send SRBs with the following <b>Function</b> values to the system port driver:

<ul>
<li>
SRB_FUNCTION_CLAIM_DEVICE to indicate that the class driver supports a peripheral identified in the SRB by the <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b> members.

</li>
<li>
SRB_ATTACH_DEVICE to indicate that a filter driver, layered above a class driver, wants requests for a particular peripheral to be routed first to the filter driver.

</li>
<li>
SRB_FUNCTION_RELEASE_DEVICE to indicate that a class driver is releasing its claim on a particular peripheral.

</li>
<li>
SRB_FUNCTION_FLUSH_QUEUE to request cancellation of any requests currently queued in the port driver to a particular peripheral.

</li>
<li>
SRB_FUNCTION_RELEASE_QUEUE to request that the port driver release a frozen queue of requests to a particular peripheral.

</li>
</ul>
The preceding SRB_FUNCTION_<i>XXX</i>  are never set in SRBs sent to SCSI miniport drivers. SRB_FUNCTION_REMOVE_DEVICE is defined for use in future versions of the system. It, too, is never set in SRBs sent to SCSI miniport drivers. SRB_FUNCTION_WMI_REQUEST is valid only in SCSI_WMI_REQUEST_BLOCK. A storage class or filter driver uses this to send WMI requests to the port driver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545387">ExInterlockedFreeToZone</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557456">HW_INITIALIZATION_DATA (SCSI)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563900">PORT_CONFIGURATION_INFORMATION (SCSI)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565397">SCSI_WMI_REQUEST_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566339">SRB_IO_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564636">ScsiPortGetPhysicalAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564637">ScsiPortGetSrb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564649">ScsiPortIoMapTransfer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564657">ScsiPortNotification</a>
 

 

