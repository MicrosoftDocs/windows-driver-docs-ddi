---
UID: NS:srb._SCSI_REQUEST_BLOCK
title: _SCSI_REQUEST_BLOCK
author: windows-driver-content
description: SCSI_REQUEST_BLOCK structure
old-location: storage\scsi_request_block.htm
old-project: storage
ms.assetid: ddd5180d-275c-4226-9af8-8e2ae25256e7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SCSI_REQUEST_BLOCK, *PSCSI_REQUEST_BLOCK, SCSI_REQUEST_BLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: srb.h
req.include-header: Srb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCSI_REQUEST_BLOCK
req.alt-loc: srb.h
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
req.typenames: *PSCSI_REQUEST_BLOCK, SCSI_REQUEST_BLOCK
req.product: Windows 10 or later.
---

# _SCSI_REQUEST_BLOCK structure



## -description

## -syntax

````
typedef struct _SCSI_REQUEST_BLOCK {
  USHORT                     Length;
  UCHAR                      Function;
  UCHAR                      SrbStatus;
  UCHAR                      ScsiStatus;
  UCHAR                      PathId;
  UCHAR                      TargetId;
  UCHAR                      Lun;
  UCHAR                      QueueTag;
  UCHAR                      QueueAction;
  UCHAR                      CdbLength;
  UCHAR                      SenseInfoBufferLength;
  ULONG                      SrbFlags;
  ULONG                      DataTransferLength;
  ULONG                      TimeOutValue;
  PVOID                      DataBuffer;
  PVOID                      SenseInfoBuffer;
  struct _SCSI_REQUEST_BLOCK  *NextSrb;
  PVOID                      OriginalRequest;
  PVOID                      SrbExtension;
  union {
    ULONG InternalStatus;
    ULONG QueueSortKey;
    ULONG LinkTimeoutValue;
  };
#ifdef _WIN64
  ULONG                      Reserved;
#endif 
  UCHAR                      Cdb[16];
} SCSI_REQUEST_BLOCK, *PSCSI_REQUEST_BLOCK;
````


## -struct-fields

### -field Length

Specifies the size in bytes of this structure.


### -field Function

Specifies the operation to be performed, which can be one of the following values:


### -field SRB_FUNCTION_EXECUTE_SCSI (0x00)

<dd>
A SCSI device I/O request should be executed on the target logical unit.


### -field SRB_FUNCTION_ABORT_COMMAND (0x10)

<dd>
A SCSIMESS_ABORT message should be sent to cancel the request pointed to by the <b>NextSrb</b> member. If this is a tagged-queue request, a SCSIMESS_ABORT_WITH_TAG message should be used instead. If the indicated request has been completed, this request should be completed normally. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b>, <b>Lun</b>, and <b>NextSrb</b> members are valid.


### -field SRB_FUNCTION_RESET_DEVICE (0x13)

<dd>
The ScsiPort driver no longer sends this SRB to its miniports. Only Storport miniport drivers use this SRB. The SCSI target controller should be reset using the SCSIMESS_BUS_DEVICE_RESET message. The miniport driver should complete any active requests for the target controller. Only the SRB <b>Function</b>, <b>TargetId</b>, and <b>PathId</b> members are valid.


### -field SRB_FUNCTION_RESET_LOGICAL_UNIT (0x20)

<dd>
The logical unit should be reset, if possible. The HBA miniport driver should complete any active requests for the logical unit. Only the <b>Function</b>, <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b> members of the SRB are valid. Storport supports this type of reset, but SCSI port does not. 


### -field SRB_FUNCTION_RESET_BUS (0x12)

<dd>
The SCSI bus should be reset using the SCSIMESS_BUS_DEVICE_RESET message. A miniport driver receives this request only if a given request has timed out and a subsequent request to abort the timed-out request also has timed out. Only the SRB <b>Function</b> and <b>PathId</b> members are valid.


### -field SRB_FUNCTION_TERMINATE_IO (0x14)

<dd>
A SCSIMESS_TERMINATE_IO_PROCESS message should be sent to cancel the request pointed to by the <b>NextSrb</b> member. If the indicated request has already completed, this request should be completed normally. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b>, <b>Lun</b>, and <b>NextSrb</b> members are valid.


### -field SRB_FUNCTION_RELEASE_RECOVERY (0x11)

<dd>
A SCSIMESS_RELEASE_RECOVERY message should be sent to the target controller. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b> members are valid.


### -field SRB_FUNCTION_RECEIVE_EVENT (0x03)

<dd>
The HBA should be prepared to receive an asynchronous event notification from the addressed target. The SRB <b>DataBuffer</b> member indicates where the data should be placed.


### -field SRB_FUNCTION_SHUTDOWN (0x07)

<dd>
The system is being shut down. This request is sent to a miniport driver only if it set <b>CachesData</b> to <b>TRUE</b> in the PORT_CONFIGURATION_INFORMATION for the HBA. Such a miniport driver can receive several of these notifications before all system activity actually stops. However, the last shutdown notification will occur after the last start I/O. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b> and <b>Lun</b> members are valid.


### -field SRB_FUNCTION_FLUSH (0x08)

<dd>
The miniport driver should flush any cached data for the target device. This request is sent to the miniport driver only if it set <b>CachesData</b> to <b>TRUE</b> in the PORT_CONFIGURATION_INFORMATION for the HBA. Only the SRB <b>Function</b>, <b>PathId</b>, <b>TargetId</b> and <b>Lun</b> members are valid.


### -field SRB_FUNCTION_IO_CONTROL (0x02)

<dd>
The request is an I/O control request, originating in a user-mode application with a dedicated HBA. The SRB <b>DataBuffer</b> points to an SRB_IO_CONTROL header followed by the data area. The value in <b>DataBuffer</b> can be used by the driver, regardless of the value of <b>MapBuffers</b>. Only the SRB <b>Function</b>, <b>SrbFlags</b>, <b>TimeOutValue</b>, <b>DataBuffer</b>, and <b>DataTransferLength</b> members are valid, along with the <b>SrbExtension</b> member if the miniport driver requested SRB extensions when it initialized. If a miniport driver controls an application-dedicated HBA so it supports this request, the miniport driver should execute the request and notify the OS-specific port driver when the SRB has completed, using the normal mechanism of calls to <a href="..\srb\nf-srb-scsiportnotification.md">ScsiPortNotification</a> with <b>RequestComplete</b> and <b>NextRequest</b>.


### -field SRB_FUNCTION_LOCK_QUEUE (0x18)

<dd>
Holds requests queued by the port driver for a particular logical unit, typically while a power request is being processed. Only the SRB <b>Length</b>, <b>Function</b>, <b>SrbFlags</b>, and <b>OriginalRequest</b> members are valid. When the queue is locked, only requests with <b>SrbFlags</b> ORed with SRB_FLAGS_BYPASS_LOCKED_QUEUE will be processed. SCSI miniport drivers do not process SRB_FUNCTION_LOCK_QUEUE requests. 


### -field SRB_FUNCTION_UNLOCK_QUEUE (0x19)

<dd>
Releases the port driver's queue for a logical unit that was previously locked with SRB_FUNCTION_LOCK_QUEUE. The <b>SrbFlags</b> of the unlock request must be ORed with SRB_FLAGS_BYPASS_LOCKED_QUEUE. Only the SRB <b>Length</b>, <b>Function</b>, <b>SrbFlags</b>, and <b>OriginalRequest</b> members are valid. SCSI miniport drivers do not process SRB_FUNCTION_UNLOCK_QUEUE requests.


### -field SRB_FUNCTION_DUMP_POINTERS (0x26)

<dd>
A request with this function is sent to a Storport miniport driver that is used to control the disk that holds the crash dump data. The request collects information needed from the miniport driver to support crash dump and hibernation. See the <b>MINIPORT_DUMP_POINTERS</b> structure. A physical miniport driver must set the STOR_FEATURE_DUMP_POINTERS flag in the <b>FeatureSupport</b> member of its <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> to receive a request with this function.


### -field SRB_FUNCTION_FREE_DUMP_POINTERS (0x27)

<dd>
A request with this function is sent to a Storport miniport driver to release any resources allocated during a previous request for SRB_FUNCTION_DUMP_POINTERS.

</dd>
</dl>

### -field SrbStatus

Returns the status of the completed request. This member should be set by the miniport driver before it notifies the OS-specific driver that the request has completed by calling <a href="..\srb\nf-srb-scsiportnotification.md">ScsiPortNotification</a> with <b>RequestComplete</b>. The value of this member can be one of the following:


### -field SRB_STATUS_PENDING

<dd>
Indicates the request is in progress. The OS-specific port driver initializes <b>SrbStatus</b> to this value.


### -field SRB_STATUS_SUCCESS

<dd>
Indicates the request was completed successfully.


### -field SRB_STATUS_ABORTED

<dd>
Indicates the request was aborted as directed by the port driver. A miniport driver sets this status in the <b>NextSrb</b> for a successful SRB_FUNCTION_ABORT_COMMAND request.


### -field SRB_STATUS_ABORT_FAILED

<dd>
Indicates an attempt to abort the request failed. Return this status for an SRB_FUNCTION_ABORT_COMMAND request when the specified request cannot be located.


### -field SRB_STATUS_ERROR

<dd>
Indicates the request was completed with an error in the SCSI bus status.


### -field SRB_STATUS_BUSY

<dd>
Indicates the miniport driver or target device could not accept the request at this time. The OS-specific port driver will resubmit the request later.


### -field SRB_STATUS_INTERNAL_ERROR

<dd>
Indicates that the SCSI Port driver could not deliver the request to the miniport driver or target device. In such cases, status is recorded in <b>InternalStatus</b>.


### -field SRB_STATUS_INVALID_REQUEST

<dd>
Indicates the miniport driver does not support the given request.


### -field SRB_STATUS_NO_DEVICE

<dd>
Indicates the device did not respond.


### -field SRB_STATUS_TIMEOUT

<dd>
Indicates the request timed out.


### -field SRB_STATUS_SELECTION_TIMEOUT

<dd>
Indicates the SCSI device selection timed out.


### -field SRB_STATUS_COMMAND_TIMEOUT

<dd>
Indicates the target did not complete the command within the time limit.


### -field SRB_STATUS_MESSAGE_REJECTED

<dd>
Indicates the target rejected a message. This is normally returned only for such message-type requests as SRB_FUNCTION_TERMINATE_IO.


### -field SRB_STATUS_BUS_RESET

<dd>
Indicates a bus reset occurred while this request was being executed.


### -field SRB_STATUS_PARITY_ERROR

<dd>
Indicates a parity error occurred on the SCSI bus and that a retry failed.


### -field SRB_STATUS_REQUEST_SENSE_FAILED

<dd>
Indicates the request-sense command failed. This is returned only if the HBA performs auto request sense and the miniport driver set <b>AutoRequestSense</b> to <b>TRUE</b> in the PORT_CONFIGURATION_INFORMATION for this HBA.


### -field SRB_STATUS_NO_HBA

<dd>
Indicates the HBA does not respond.


### -field SRB_STATUS_DATA_OVERRUN

<dd>
Indicates that a data overrun or underrun error occurred. The miniport driver also must update the SRB's <b>DataTransferLength</b> member to indicate how much data actually was transferred if an underrun occurs. 


### -field SRB_STATUS_UNEXPECTED_BUS_FREE

<dd>
Indicates the target disconnected unexpectedly.


### -field SRB_STATUS_PHASE_SEQUENCE_FAILURE

<dd>
Indicates the HBA detected an illegal phase sequence failure error.


### -field SRB_STATUS_REQUEST_FLUSHED

<dd>
Indicates the request for status was stopped.


### -field SRB_STATUS_BAD_FUNCTION

<dd>
Indicates the SRB <b>Function</b> code is not supported.


### -field SRB_STATUS_INVALID_PATH_ID

<dd>
Indicates the <b>PathId</b> specified in the SRB does not exist.


### -field SRB_STATUS_INVALID_TARGET_ID

<dd>
Indicates the <b>TargetID</b> value in the SRB is invalid.


### -field SRB_STATUS_INVALID_LUN

<dd>
Indicates the <b>Lun</b> value in the SRB is invalid.


### -field SRB_STATUS_ERROR_RECOVERY

<dd>
Indicates the request was completed with an error in the SCSI bus status and that the SCSI INITIATE RECOVERY message was received.


### -field SRB_STATUS_AUTOSENSE_VALID

<dd>
Indicates information returned in the <b>SenseInfoBuffer</b> is valid.


### -field SRB_STATUS_QUEUE_FROZEN

<dd>
A miniport driver should <i>never</i> set the <b>SrbStatus</b> member to this value. The Windows port driver can set this value to inform a storage class driver that its queue of requests for a particular peripheral has been frozen. 

</dd>
</dl>

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


### -field SRB_FLAGS_QUEUE_ACTION_ENABLE

<dd>
Indicates tagged-queue actions are to be enabled.


### -field SRB_FLAGS_DISABLE_AUTOSENSE

<dd>
Indicates that request-sense information should not be returned.


### -field SRB_FLAGS_DATA_IN

<dd>
Indicates data will be transferred from the device to the system.


### -field SRB_FLAGS_DATA_OUT

<dd>
Indicates data will be transferred from the system to the device.


### -field SRB_FLAGS_UNSPECIFIED_DIRECTION

<dd>
Defined for backward compatibility with the ASPI/CAM SCSI interfaces, this flag indicates that the transfer direction could be either of the preceding because both of the preceding flags are set. If this flag is set, a miniport driver should determine the transfer direction by examining the data phase for the target on the SCSI bus. If its HBA is a subordinate DMA device, such a miniport driver must update SRB_FLAGS_DATA_OUT or SRB_FLAGS_DATA_IN to the correct value before it calls <a href="..\srb\nf-srb-scsiportiomaptransfer.md">ScsiPortIoMapTransfer</a>.


### -field SRB_FLAGS_NO_DATA_TRANSFER

<dd>
Indicates no data transfer with this request. If this is set, the flags SRB_FLAGS_DATA_OUT, SRB_FLAGS_DATA_IN, and SRB_FLAGS_UNSPECIFIED_DIRECTION are clear.


### -field SRB_FLAGS_DISABLE_SYNCH_TRANSFER

<dd>
Indicates the HBA, if possible, should perform asynchronous I/O for this transfer request. If synchronous I/O was negotiated previously, the HBA must renegotiate for asynchronous I/O before performing the transfer.


### -field SRB_FLAGS_DISABLE_DISCONNECT

<dd>
Indicates the HBA should not allow the target to disconnect from the SCSI bus during processing of this request.


### -field SRB_FLAGS_BYPASS_FROZEN_QUEUE

<dd>
Is irrelevant to miniport drivers.


### -field SRB_FLAGS_NO_QUEUE_FREEZE

<dd>
Is irrelevant to miniport drivers.


### -field SRB_FLAGS_IS_ACTIVE

<dd>
Is irrelevant to miniport drivers.


### -field SRB_FLAGS_ALLOCATED_FROM_ZONE

<dd>
Is irrelevant to miniport drivers and is obsolete to current Windows class drivers. To a Windows legacy class driver, this indicates whether the SRB was allocated from a zone buffer. If this flag is set, the class driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545387">ExInterlockedFreeToZone</a> to release the SRB; otherwise, it must call <a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>. New class drivers should use lookaside lists rather than zone buffers.


### -field SRB_FLAGS_SGLIST_FROM_POOL

<dd>
Is irrelevant to miniport drivers. To a Windows class driver, this indicates that memory for a scatter/gather list was allocated from nonpaged pool. If this flag is set, the class driver must call <a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a> to release the memory after the SRB is completed. 


### -field SRB_FLAGS_BYPASS_LOCKED_QUEUE

<dd>
Is irrelevant to miniport drivers. To the port driver, this flag indicates that the request should be processed whether the logical-unit queue is locked. A higher-level driver must set this flag to send an SRB_FUNCTION_UNLOCK_QUEUE request.


### -field SRB_FLAGS_NO_KEEP_AWAKE

<dd>
Is irrelevant to miniport drivers. A Windows  class driver uses this flag to indicate to the port driver to report idle rather than powering up the device to handle this request.


### -field SRB_FLAGS_FREE_SENSE_BUFFER

<dd>
Indicates that either the port or the miniport driver has allocated a buffer for sense data. This informs the class driver that it must free the sense data buffer after extracting the data.

</dd>
</dl>

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

Points to the Srb extension. A miniport driver must not use this member if it set <b>SrbExtensionSize</b> to zero in the SCSI_HW_INITIALIZATION_DATA. The memory at <b>SrbExtension</b> is not initialized by the OS-specific port driver, and the miniport driver-determined data can be accessed directly by the HBA. The corresponding physical address can be obtained by calling <a href="..\srb\nf-srb-scsiportgetphysicaladdress.md">ScsiPortGetPhysicalAddress</a> with the <b>SrbExtension</b> pointer.


### -field InternalStatus

Used by the SCSI Port driver, instead of <b>SrbStatus</b>, to report the status of the completed request whenever the request cannot be delivered to the miniport driver. In such cases, <b>SrbStatus</b> is set to SRB_STATUS_INTERNAL_ERROR. This member is used exclusively for communication between the SCSI Port and the class driver and should not be used by miniport drivers.


### -field QueueSortKey

Specifies the offset from the start of the media or zero, depending on the type of the target device. 


### -field LinkTimeoutValue


### -field offset 2c 

</dl>

### -field Reserved

Reserved.


### -field Cdb

Specifies the SCSI-2 or later command descriptor block to be sent to the target device. 


## -remarks
Windows storage class and filter drivers can send SRBs with the following <b>Function</b> values to the system port driver:

SRB_FUNCTION_CLAIM_DEVICE to indicate that the class driver supports a peripheral identified in the SRB by the <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b> members.

SRB_ATTACH_DEVICE to indicate that a filter driver, layered above a class driver, wants requests for a particular peripheral to be routed first to the filter driver.

SRB_FUNCTION_RELEASE_DEVICE to indicate that a class driver is releasing its claim on a particular peripheral.

SRB_FUNCTION_FLUSH_QUEUE to request cancellation of any requests currently queued in the port driver to a particular peripheral.

SRB_FUNCTION_RELEASE_QUEUE to request that the port driver release a frozen queue of requests to a particular peripheral.

The preceding SRB_FUNCTION_<i>XXX</i>  are never set in SRBs sent to SCSI miniport drivers. SRB_FUNCTION_REMOVE_DEVICE is defined for use in future versions of the system. It, too, is never set in SRBs sent to SCSI miniport drivers. SRB_FUNCTION_WMI_REQUEST is valid only in SCSI_WMI_REQUEST_BLOCK. A storage class or filter driver uses this to send WMI requests to the port driver.


## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545387">ExInterlockedFreeToZone</a>
</dt>
<dt>
<a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a>
</dt>
<dt>
<a href="..\srb\ns-srb-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION (SCSI)</a>
</dt>
<dt>
<a href="..\srb\ns-srb-_scsi_wmi_request_block.md">SCSI_WMI_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="..\srb\nf-srb-scsiportgetphysicaladdress.md">ScsiPortGetPhysicalAddress</a>
</dt>
<dt>
<a href="..\srb\nf-srb-scsiportgetsrb.md">ScsiPortGetSrb</a>
</dt>
<dt>
<a href="..\srb\nf-srb-scsiportiomaptransfer.md">ScsiPortIoMapTransfer</a>
</dt>
<dt>
<a href="..\srb\nf-srb-scsiportnotification.md">ScsiPortNotification</a>
</dt>
<dt>
<a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSI_REQUEST_BLOCK structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

