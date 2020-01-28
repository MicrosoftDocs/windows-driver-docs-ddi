---
UID: NS:srb._STORAGE_REQUEST_BLOCK
title: _STORAGE_REQUEST_BLOCK (srb.h)
description: The STORAGE_REQUEST_BLOCK is the extended format SCSI Request Block (SRB) structure.
old-location: storage\storage_request_block.htm
tech.root: storage
ms.assetid: 67A5077D-B1AD-49B7-B024-D139E375483F
ms.date: 03/29/2018
ms.keywords: PSTORAGE_REQUEST_BLOCK, PSTORAGE_REQUEST_BLOCK structure pointer [Storage Devices], SRB_FLAGS_ADAPTER_CACHE_ENABLE, SRB_FLAGS_ALLOCATED_FROM_ZONE, SRB_FLAGS_BYPASS_FROZEN_QUEUE, SRB_FLAGS_BYPASS_LOCKED_QUEUE, SRB_FLAGS_D3_PROCESSING, SRB_FLAGS_DATA_IN, SRB_FLAGS_DATA_OUT, SRB_FLAGS_DISABLE_AUTOSENSE, SRB_FLAGS_DISABLE_DISCONNECT, SRB_FLAGS_DISABLE_SYNCH_TRANSFER, SRB_FLAGS_FREE_SENSE_BUFFER, SRB_FLAGS_IS_ACTIVE, SRB_FLAGS_NO_DATA_TRANSFER, SRB_FLAGS_NO_KEEP_AWAKE, SRB_FLAGS_NO_QUEUE_FREEZE, SRB_FLAGS_QUEUE_ACTION_ENABLE, SRB_FLAGS_SGLIST_FROM_POOL, SRB_FLAGS_UNSPECIFIED_DIRECTION, SRB_FUNCTION_ABORT_COMMAND, SRB_FUNCTION_CRYPTO_OPERATION, SRB_FUNCTION_DUMP_POINTERS, SRB_FUNCTION_EXECUTE_SCSI, SRB_FUNCTION_FLUSH, SRB_FUNCTION_FREE_DUMP_POINTERS, SRB_FUNCTION_IO_CONTROL, SRB_FUNCTION_LOCK_QUEUE, SRB_FUNCTION_PNP, SRB_FUNCTION_POWER, SRB_FUNCTION_QUIESCE_DEVICE, SRB_FUNCTION_RECEIVE_EVENT, SRB_FUNCTION_RELEASE_RECOVERY, SRB_FUNCTION_RESET_BUS, SRB_FUNCTION_RESET_DEVICE, SRB_FUNCTION_RESET_LOGICAL_UNIT, SRB_FUNCTION_SHUTDOWN, SRB_FUNCTION_TERMINATE_IO, SRB_FUNCTION_UNLOCK_QUEUE, SRB_FUNCTION_WMI, SRB_STATUS_ABORTED, SRB_STATUS_ABORT_FAILED, SRB_STATUS_AUTOSENSE_VALID, SRB_STATUS_BAD_FUNCTION, SRB_STATUS_BAD_SRB_BLOCK_LENGTH, SRB_STATUS_BUSY, SRB_STATUS_BUS_RESET, SRB_STATUS_COMMAND_TIMEOUT, SRB_STATUS_DATA_OVERRUN, SRB_STATUS_ERROR, SRB_STATUS_ERROR_RECOVERY, SRB_STATUS_INTERNAL_ERROR, SRB_STATUS_INVALID_LUN, SRB_STATUS_INVALID_PATH_ID, SRB_STATUS_INVALID_REQUEST, SRB_STATUS_INVALID_TARGET_ID, SRB_STATUS_LINK_DOWN, SRB_STATUS_MESSAGE_REJECTED, SRB_STATUS_NOT_POWERED, SRB_STATUS_NO_DEVICE, SRB_STATUS_NO_HBA, SRB_STATUS_PARITY_ERROR, SRB_STATUS_PENDING, SRB_STATUS_PHASE_SEQUENCE_FAILURE, SRB_STATUS_QUEUE_FROZEN, SRB_STATUS_REQUEST_FLUSHED, SRB_STATUS_REQUEST_SENSE_FAILED, SRB_STATUS_SELECTION_TIMEOUT, SRB_STATUS_SUCCESS, SRB_STATUS_TIMEOUT, SRB_STATUS_UNEXPECTED_BUS_FREE, STORAGE_REQUEST_BLOCK, STORAGE_REQUEST_BLOCK structure [Storage Devices], _STORAGE_REQUEST_BLOCK, storage.storage_request_block, storport/PSTORAGE_REQUEST_BLOCK, storport/STORAGE_REQUEST_BLOCK
f1_keywords:
 - "srb/STORAGE_REQUEST_BLOCK"
req.header: srb.h
req.include-header: Storport.h, Srb.h, Minitape.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Storport.h
api_name:
- STORAGE_REQUEST_BLOCK
product:
- Windows
targetos: Windows
req.typenames: STORAGE_REQUEST_BLOCK, PSTORAGE_REQUEST_BLOCK
---

# _STORAGE_REQUEST_BLOCK structure


## -description



   The <b>STORAGE_REQUEST_BLOCK</b> is the extended format SCSI Request Block (SRB) structure. The structure provides for the addition of extended data associated with an SRB function.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Length

Specifies the size of the SRB header for compatibility with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a> structure. This is equal to the offset of the <b>Signature</b> member of this structure.


### -field Function

Set to <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b> to indicate that this is an extended SRB. Unlike in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>, the SRB function identifier is in the <b>SrbFunction</b> member instead.


### -field SrbStatus

Returns the status of the completed request. This member should be set by the miniport driver before it notifies the operating system-specific driver that the request has completed by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportnotification">StorPortNotification</a> with <b>RequestComplete</b>. The value of this member can be one of the following:



#### SRB_STATUS_PENDING

Indicates the request is in progress. The operating system-specific port driver initializes <b>SrbStatus</b> to this value.



#### SRB_STATUS_SUCCESS

Indicates the request was completed successfully.



#### SRB_STATUS_ABORTED

Indicates the request was aborted as directed by the port driver. A miniport driver sets this status in the <b>NextSrb</b> member for a successful SRB_FUNCTION_ABORT_COMMAND request.



#### SRB_STATUS_ABORT_FAILED

Indicates an attempt to abort the request failed. Return this status for an SRB_FUNCTION_ABORT_COMMAND request when the specified request cannot be located.



#### SRB_STATUS_ERROR

Indicates the request was completed with an error in the SCSI bus status.



#### SRB_STATUS_BUSY

Indicates the miniport driver or target device could not accept the request at this time. The operating system-specific port driver will resubmit the request later.



#### SRB_STATUS_INTERNAL_ERROR

Indicates that the Storport driver could not deliver the request to the miniport driver or target device. In such cases, status is recorded in <b>InternalStatus</b>.



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

Indicates the request-sense command failed. This is returned only if the host bus adapter (HBA) performs auto request sense and the miniport driver set <b>AutoRequestSense</b> to <b>TRUE</b> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> for this HBA.



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

A miniport driver should never set the <b>SrbStatus</b> member to this value. The Windows  port driver can set this value to inform a storage class driver that its queue of requests for a particular peripheral has been frozen. 



#### SRB_STATUS_NOT_POWERED

A indicates the request failed because the target is not powered. For requests with SRB_FLAGS_NO_KEEP_AWAKE set in <b>SrbFlags</b>, requests sent to LUNs that are powered down will fail with this status.



#### SRB_STATUS_LINK_DOWN

Indicates the request failed because link is down.



#### SRB_STATUS_BAD_SRB_BLOCK_LENGTH

Indicates the request failed because SRB length was invalid.


### -field ReservedUchar

Reserved. Set to 0.


### -field Signature

The signature of the extended SRB format. This is set to SRB_SIGNATURE.


### -field Version

The version of the structure used. The current version is <b>STORAGE_REQUEST_BLOCK_VERSION_1</b>.


### -field SrbLength

The length of this extended SRB, in bytes, including this structure, address and any SRB extended data.


### -field SrbFunction

Specifies the operation to be performed, which can be one of these values:



#### SRB_FUNCTION_EXECUTE_SCSI (0x00)

A SCSI device I/O request should be executed on the target logical unit. When <b>NumSrbExData</b> > 0, one or more following extended request block structures are located at the offsets specified in <b>SrbExDataOffset</b>.

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_srbex_data_scsi_cdb16">SRBEX_DATA_SCSI_CDB16</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_srbex_data_scsi_cdb32">SRBEX_DATA_SCSI_CDB32</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_srbex_data_scsi_cdb_var">SRBEX_DATA_SCSI_CDB_VAR</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_srbex_data_bidirectional">SRBEX_DATA_BIDIRECTIONAL</a>
<b>Cdb</b>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_srbex_data_io_info">SRBEX_DATA_IO_INFO</a>
<b>Cdb</b>


#### SRB_FUNCTION_ABORT_COMMAND (0x10)

A SCSIMESS_ABORT message should be sent to cancel the request pointed to by the <b>NextSrb</b> member. If this is a tagged-queue request, a SCSIMESS_ABORT_WITH_TAG message should be used instead. If the indicated request has been completed, this request should be completed normally. Extended SRB data is not required for this function.

<div class="alert"><b>Note</b>  This function is not sent to the miniport by Storport.</div>
<div> </div>


#### SRB_FUNCTION_RESET_DEVICE (0x16)

 The SCSI target controller should be reset using the SCSIMESS_BUS_DEVICE_RESET message. The miniport driver should complete any active requests for the target controller. Extended SRB data is not required for this function.



#### SRB_FUNCTION_RESET_LOGICAL_UNIT (0x20)

The logical unit should be reset, if possible. The HBA miniport driver should complete any active requests for the logical unit. Extended SRB data is not required for this function. Storport supports this type of reset, but SCSI port does not. 



#### SRB_FUNCTION_RESET_BUS (0x12)

The SCSI bus should be reset using the SCSIMESS_BUS_DEVICE_RESET message. A miniport driver receives this request only if a given request has timed out and a subsequent request to abort the timed-out request also has timed out. Extended SRB data is not required for this function.



#### SRB_FUNCTION_TERMINATE_IO (0x14)

A SCSIMESS_TERMINATE_IO_PROCESS message should be sent to cancel the request pointed to by the <b>NextSrb</b> member. If the indicated request has already completed, this request should be completed normally. Extended SRB data is not required for this function.

<div class="alert"><b>Note</b>  This function is not sent to the miniport by Storport.</div>
<div> </div>


#### SRB_FUNCTION_RELEASE_RECOVERY (0x11)

A SCSIMESS_RELEASE_RECOVERY message should be sent to the target controller. Extended SRB data is not required for this function.

<div class="alert"><b>Note</b>  This function is not sent to the miniport by Storport.</div>
<div> </div>


#### SRB_FUNCTION_RECEIVE_EVENT (0x03)

The HBA should be prepared to receive an asynchronous event notification from the addressed target. The SRB <b>DataBuffer</b> member indicates where the data should be placed.

<div class="alert"><b>Note</b>  This function is not sent to the miniport by Storport.</div>
<div> </div>


#### SRB_FUNCTION_SHUTDOWN (0x07)

The system is being shut down. A miniport driver can receive several of these notifications before all system activity actually stops. However, the last shutdown notification will occur after the last start I/O. Extended SRB data is not required for this function.



#### SRB_FUNCTION_FLUSH (0x08)

The miniport driver should flush any cached data for the target device. This request is sent to the miniport driver only if it set <b>CachesData</b> to <b>TRUE</b> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> for the HBA. Extended SRB data is not required for this function.



#### SRB_FUNCTION_IO_CONTROL (0x02)

The request is an I/O control request, originating in a user-mode application with a dedicated HBA. The SRB <b>DataBuffer</b> points to an <b>SRB_IO_CONTROL</b> header followed by the data area. The value in <b>DataBuffer</b> can be used by the driver, regardless of the value of <b>MapBuffers</b>. Only the SRB <b>Function</b>, <b>SrbFlags</b>, <b>TimeOutValue</b>, <b>DataBuffer</b>, and <b>DataTransferLength</b> members are valid, along with the <b>SrbExtension</b> member if the miniport driver requested SRB extensions when it initialized. If a miniport driver controls an application-dedicated HBA so that it supports this request, the miniport driver should execute the request and notify the operating system-specific port driver when the SRB has completed, using the normal mechanism of calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportnotification">StorPortNotification</a> with <b>RequestComplete</b> and <b>NextRequest</b>.



#### SRB_FUNCTION_LOCK_QUEUE (0x18)

Holds requests that are queued by the port driver for a particular logical unit, typically while a power request is being processed. Only the SRB <b>Length</b>, <b>Function</b>, <b>SrbFlags</b>, and <b>OriginalRequest</b> members are valid. When the queue is locked, only requests with <b>SrbFlags</b> ORed with <b>SRB_FLAGS_BYPASS_LOCKED_QUEUE</b> will be processed. SCSI miniport drivers do not process <b>SRB_FUNCTION_LOCK_QUEUE</b> requests. 



#### SRB_FUNCTION_UNLOCK_QUEUE (0x19)

Releases the port driver's queue for a logical unit that was previously locked with <b>SRB_FUNCTION_LOCK_QUEUE</b>. The <b>SrbFlags</b> of the unlock request must be ORed with <b>SRB_FLAGS_BYPASS_LOCKED_QUEUE</b>. Only the SRB <b>Length</b>, <b>Function</b>, <b>SrbFlags</b>, and <b>OriginalRequest</b> members are valid. SCSI miniport drivers do not process <b>SRB_FUNCTION_UNLOCK_QUEUE</b> requests.



#### SRB_FUNCTION_DUMP_POINTERS (0x26)

A request with this function is sent to a Storport miniport driver that is used to control the disk that holds the crash dump data. The request collects information needed from the miniport driver to support crash dump and hibernation. See the <b>MINIPORT_DUMP_POINTERS</b> structure. A physical miniport driver must set the STOR_FEATURE_DUMP_POINTERS flag in the <b>FeatureSupport</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> to receive a request with this function.



#### SRB_FUNCTION_FREE_DUMP_POINTERS (0x27)

A request with this function is sent to a Storport miniport driver to release any resources allocated during a previous request for SRB_FUNCTION_DUMP_POINTERS.



#### SRB_FUNCTION_QUIESCE_DEVICE (0x1A)

The request is only between a storage class and storage port driver and is not be sent to miniport. The this function serves as a wait by the class driver for port driver to complete all outstanding I/Os.



#### SRB_FUNCTION_PNP (0x25)

The request is a PnP extended request formatted as a <b>SRBEX_DATA_PNP</b> structure. The offset to extended request data is located at <b>SrbExDataOffset</b>[0].



#### SRB_FUNCTION_POWER (0x24)

The request is a power extended request formatted as a <b>SRBEX_DATA_POWER</b> structure. The offset to extended request data is located at <b>SrbExDataOffset</b>[0].



#### SRB_FUNCTION_WMI (0x17)

The request is a power extended request formatted as a <b>SRBEX_DATA_WMI</b> structure. The offset to extended request data is located at <b>SrbExDataOffset</b>[0].



#### SRB_FUNCTION_CRYPTO_OPERATION ()

Reserved for system use.


### -field SrbFlags

Indicates various parameters and options for the request. <b>SrbFlags</b> is read-only, except when <b>SRB_FLAGS_UNSPECIFIED_DIRECTION</b> is set and miniport drivers of subordinate DMA adapters are required to update <b>SRB_FLAGS_DATA_IN</b> or <b>SRB_FLAGS_DATA_OUT</b>. This member can have one or more of these flags set:



#### SRB_FLAGS_QUEUE_ACTION_ENABLE

Indicates tagged-queue actions are to be enabled.



#### SRB_FLAGS_DISABLE_AUTOSENSE

Indicates request-sense information should not be returned.



#### SRB_FLAGS_DATA_IN

Indicates data will be transferred from the device to the system.



#### SRB_FLAGS_DATA_OUT

Indicates data will be transferred from the system to the device.



#### SRB_FLAGS_UNSPECIFIED_DIRECTION

Defined for backward compatibility with the ASPI/CAM SCSI interfaces, this flag indicates that the transfer direction could be either of the preceding, because both of the preceding flags are set. If this flag is set, a miniport driver should determine the transfer direction by examining the data phase for the target on the SCSI bus.



#### SRB_FLAGS_NO_DATA_TRANSFER

Indicates no data transfer with this request. If this is set, the flags <b>SRB_FLAGS_DATA_OUT</b>, <b>SRB_FLAGS_DATA_IN</b>, and <b>SRB_FLAGS_UNSPECIFIED_DIRECTION</b> are clear.



#### SRB_FLAGS_DISABLE_SYNCH_TRANSFER

Indicates the HBA, if possible, should perform asynchronous I/O for this transfer request. If synchronous I/O was negotiated previously, the HBA must renegotiate for asynchronous I/O before performing the transfer.



#### SRB_FLAGS_DISABLE_DISCONNECT

Indicates the HBA should not allow the target to disconnect from the SCSI bus during processing of this request.



#### SRB_FLAGS_BYPASS_FROZEN_QUEUE

This flag is irrelevant to miniport drivers.



#### SRB_FLAGS_NO_QUEUE_FREEZE

This flag is irrelevant to miniport drivers.



#### SRB_FLAGS_IS_ACTIVE

This flag is irrelevant to miniport drivers.



#### SRB_FLAGS_ALLOCATED_FROM_ZONE

This flag is irrelevant to miniport drivers and is obsolete to new Windows class drivers. To a Windows legacy class driver, this indicates whether the SRB was allocated from a zone buffer. If this flag is set, the class driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mmcreatemdl">ExInterlockedFreeToZone</a> to release the SRB; otherwise, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>. New class drivers should use lookaside lists rather than zone buffers.



#### SRB_FLAGS_SGLIST_FROM_POOL

This flag is irrelevant to miniport drivers. To the class driver, this indicates that memory for a scatter/gather list was allocated from a nonpaged pool. If this flag is set, the class driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a> to release the memory after the SRB is completed. 



#### SRB_FLAGS_BYPASS_LOCKED_QUEUE

This flag is irrelevant to miniport drivers. To the port driver, this flag indicates that the request should be processed whether the logical-unit queue is locked or not. A higher-level driver must set this flag to send an <b>SRB_FUNCTION_UNLOCK_QUEUE</b> request.



#### SRB_FLAGS_NO_KEEP_AWAKE

This flag is irrelevant to miniport drivers. A Windows class driver uses this flag to indicate to the port driver to fail the request rather than powering up the device to handle this request.



#### SRB_FLAGS_FREE_SENSE_BUFFER

Indicates that either the port or the miniport driver has allocated a buffer for sense data. This informs the class driver that it must free the sense data buffer after extracting the data.



#### SRB_FLAGS_D3_PROCESSING

Indicates that the request is part of D3 processing. Miniports that support runtime power control should not call <b>StorPortPoFxActivateComponent</b> or <b>StorPortPoFxIdleComponent</b> with these requests



#### SRB_FLAGS_ADAPTER_CACHE_ENABLE

Indicates that the adapter can cache data.


### -field ReservedUlong

Reserved. Set to 0.


### -field RequestTag

Contains the queue-tag value assigned by the operating system-specific port driver. If this member is used for tagged queuing, the HBA supports internal queuing of requests to logical units (LUs) and the miniport driver set <b>TaggedQueueing</b> to <b>TRUE</b> in the PORT_CONFIGURATION_INFORMATION for this HBA.


### -field RequestPriority

The priority assignment for the SRB. This is one of the following **_STOR_IO_PRIORITY_HINT** values:

| Value | Meaning |
| --- | --- |
| <p>StorIoPriorityVeryLow</p><p>0</p> | Very low priority. |
| <p>StorIoPriorityLow</p><p>1</p> | Low priority.  |
| <p>StorIoPriorityNormal</p><p>2</p> | Normal priority. |
| <p>StorIoPriorityHigh</p><p>3</p> | High priority. |
| <p>StorIoPriorityCritical</p><p>4</p> | Critical priority. |

### -field RequestAttribute

Indicates the tagged-queuing message to be used when the <b>SRB_FLAGS_QUEUE_ACTION_ENABLE</b> flag is set. The value can be one of the following: <b>SRB_SIMPLE_TAG_REQUEST</b>, <b>SRB_HEAD_OF_QUEUE_TAG_REQUEST</b>, or <b>SRB_ORDERED_QUEUE_TAG_REQUEST</b>.


### -field TimeOutValue

Indicates the interval, in seconds, that the request can execute before the operating system-specific port driver might consider it timed out. Miniport drivers are not required to time requests because the port driver already does.


### -field SystemStatus

Used by the Storport driver, instead of <b>SrbStatus</b>, to report the status of the completed request whenever the request cannot be delivered to the miniport driver. In such cases, <b>SrbStatus</b> is set to <b>SRB_STATUS_INTERNAL_ERROR</b>. This member is used exclusively for communication between the Storport and the class driver and should not be used by miniport drivers.


### -field ZeroGuard1

A guard area to protect against drivers that interpret this structure as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>. Set to 0.


### -field AddressOffset

The offset of the storage request address from the beginning of this structure. This offset locates a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-_stor_address">STOR_ADDRESS</a> structure that contains the address for the request.


### -field NumSrbExData

The count of extended SRB data blocks for this request.


### -field DataTransferLength

Indicates the size, in bytes, of the data buffer. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred.


### -field DataBuffer

Points to the data buffer. Miniport drivers should not use this value as a data pointer unless the miniport driver set <b>MapBuffers</b> to <b>TRUE</b> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> for the HBA. In the case of SRB_FUNCTION_IO_CONTROL requests, however, miniport drivers can use this value as a data pointer regardless of the value of <b>MapBuffers</b>.


### -field ZeroGuard2

A guard area to protect against drivers that interpret this structure as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>. Set to 0.


### -field OriginalRequest

Points to the IRP for this request. This member is irrelevant to miniport drivers.


### -field ClassContext

Points to a class driver context data for this request. This member is irrelevant to miniport drivers.


### -field PortContext

Points to a port driver context data for this request. This member is irrelevant to miniport drivers.


### -field MiniportContext

Points to the Srb extension. A miniport driver must not use this member if it set <b>SrbExtensionSize</b> to zero in  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a>. The memory at <b>MiniportContext</b> is not initialized by the operating system-specific port driver, and the miniport driver-determined data can be accessed directly by the HBA. The corresponding physical address can be obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportgetphysicaladdress">StorportGetPhysicalAddress</a> with the <b>MiniportContext</b> pointer.


### -field NextSrb

Indicates the <b>STORAGE_REQUEST_BLOCK</b> to which this request applies. Only a small subset of requests use a second SRB, for example SRB_FUNCTION_ABORT_COMMAND.


### -field _STORAGE_REQUEST_BLOCK

 


### -field SrbExDataOffset

An array of offsets specifying the location of extended data blocks for the SRB. This array is empty if <b>NumSrbExData</b> = 0.


##### - SrbFlags.SRB_FLAGS_ADAPTER_CACHE_ENABLE

Indicates that the adapter can cache data.


##### - SrbFlags.SRB_FLAGS_ALLOCATED_FROM_ZONE

This flag is irrelevant to miniport drivers and is obsolete to new Windows class drivers. To a Windows legacy class driver, this indicates whether the SRB was allocated from a zone buffer. If this flag is set, the class driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mmcreatemdl">ExInterlockedFreeToZone</a> to release the SRB; otherwise, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>. New class drivers should use lookaside lists rather than zone buffers.


##### - SrbFlags.SRB_FLAGS_BYPASS_FROZEN_QUEUE

This flag is irrelevant to miniport drivers.


##### - SrbFlags.SRB_FLAGS_BYPASS_LOCKED_QUEUE

This flag is irrelevant to miniport drivers. To the port driver, this flag indicates that the request should be processed whether the logical-unit queue is locked or not. A higher-level driver must set this flag to send an <b>SRB_FUNCTION_UNLOCK_QUEUE</b> request.


##### - SrbFlags.SRB_FLAGS_D3_PROCESSING

Indicates that the request is part of D3 processing. Miniports that support runtime power control should not call <b>StorPortPoFxActivateComponent</b> or <b>StorPortPoFxIdleComponent</b> with these requests


##### - SrbFlags.SRB_FLAGS_DATA_IN

Indicates data will be transferred from the device to the system.


##### - SrbFlags.SRB_FLAGS_DATA_OUT

Indicates data will be transferred from the system to the device.


##### - SrbFlags.SRB_FLAGS_DISABLE_AUTOSENSE

Indicates request-sense information should not be returned.


##### - SrbFlags.SRB_FLAGS_DISABLE_DISCONNECT

Indicates the HBA should not allow the target to disconnect from the SCSI bus during processing of this request.


##### - SrbFlags.SRB_FLAGS_DISABLE_SYNCH_TRANSFER

Indicates the HBA, if possible, should perform asynchronous I/O for this transfer request. If synchronous I/O was negotiated previously, the HBA must renegotiate for asynchronous I/O before performing the transfer.


##### - SrbFlags.SRB_FLAGS_FREE_SENSE_BUFFER

Indicates that either the port or the miniport driver has allocated a buffer for sense data. This informs the class driver that it must free the sense data buffer after extracting the data.


##### - SrbFlags.SRB_FLAGS_IS_ACTIVE

This flag is irrelevant to miniport drivers.


##### - SrbFlags.SRB_FLAGS_NO_DATA_TRANSFER

Indicates no data transfer with this request. If this is set, the flags <b>SRB_FLAGS_DATA_OUT</b>, <b>SRB_FLAGS_DATA_IN</b>, and <b>SRB_FLAGS_UNSPECIFIED_DIRECTION</b> are clear.


##### - SrbFlags.SRB_FLAGS_NO_KEEP_AWAKE

This flag is irrelevant to miniport drivers. A Windows class driver uses this flag to indicate to the port driver to fail the request rather than powering up the device to handle this request.


##### - SrbFlags.SRB_FLAGS_NO_QUEUE_FREEZE

This flag is irrelevant to miniport drivers.


##### - SrbFlags.SRB_FLAGS_QUEUE_ACTION_ENABLE

Indicates tagged-queue actions are to be enabled.


##### - SrbFlags.SRB_FLAGS_SGLIST_FROM_POOL

This flag is irrelevant to miniport drivers. To the class driver, this indicates that memory for a scatter/gather list was allocated from a nonpaged pool. If this flag is set, the class driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a> to release the memory after the SRB is completed. 


##### - SrbFlags.SRB_FLAGS_UNSPECIFIED_DIRECTION

Defined for backward compatibility with the ASPI/CAM SCSI interfaces, this flag indicates that the transfer direction could be either of the preceding, because both of the preceding flags are set. If this flag is set, a miniport driver should determine the transfer direction by examining the data phase for the target on the SCSI bus.


##### - SrbFunction.SRB_FUNCTION_ABORT_COMMAND (0x10)

A SCSIMESS_ABORT message should be sent to cancel the request pointed to by the <b>NextSrb</b> member. If this is a tagged-queue request, a SCSIMESS_ABORT_WITH_TAG message should be used instead. If the indicated request has been completed, this request should be completed normally. Extended SRB data is not required for this function.

<div class="alert"><b>Note</b>  This function is not sent to the miniport by Storport.</div>
<div> </div>

##### - SrbFunction.SRB_FUNCTION_CRYPTO_OPERATION ()

Reserved for system use.


##### - SrbFunction.SRB_FUNCTION_DUMP_POINTERS (0x26)

A request with this function is sent to a Storport miniport driver that is used to control the disk that holds the crash dump data. The request collects information needed from the miniport driver to support crash dump and hibernation. See the <b>MINIPORT_DUMP_POINTERS</b> structure. A physical miniport driver must set the STOR_FEATURE_DUMP_POINTERS flag in the <b>FeatureSupport</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> to receive a request with this function.


##### - SrbFunction.SRB_FUNCTION_EXECUTE_SCSI (0x00)

A SCSI device I/O request should be executed on the target logical unit. When <b>NumSrbExData</b> > 0, one or more following extended request block structures are located at the offsets specified in <b>SrbExDataOffset</b>.

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_srbex_data_scsi_cdb16">SRBEX_DATA_SCSI_CDB16</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_srbex_data_scsi_cdb32">SRBEX_DATA_SCSI_CDB32</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_srbex_data_scsi_cdb_var">SRBEX_DATA_SCSI_CDB_VAR</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_srbex_data_bidirectional">SRBEX_DATA_BIDIRECTIONAL</a>
<b>Cdb</b>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_srbex_data_io_info">SRBEX_DATA_IO_INFO</a>
<b>Cdb</b>

##### - SrbFunction.SRB_FUNCTION_FLUSH (0x08)

The miniport driver should flush any cached data for the target device. This request is sent to the miniport driver only if it set <b>CachesData</b> to <b>TRUE</b> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> for the HBA. Extended SRB data is not required for this function.


##### - SrbFunction.SRB_FUNCTION_FREE_DUMP_POINTERS (0x27)

A request with this function is sent to a Storport miniport driver to release any resources allocated during a previous request for SRB_FUNCTION_DUMP_POINTERS.


##### - SrbFunction.SRB_FUNCTION_IO_CONTROL (0x02)

The request is an I/O control request, originating in a user-mode application with a dedicated HBA. The SRB <b>DataBuffer</b> points to an <b>SRB_IO_CONTROL</b> header followed by the data area. The value in <b>DataBuffer</b> can be used by the driver, regardless of the value of <b>MapBuffers</b>. Only the SRB <b>Function</b>, <b>SrbFlags</b>, <b>TimeOutValue</b>, <b>DataBuffer</b>, and <b>DataTransferLength</b> members are valid, along with the <b>SrbExtension</b> member if the miniport driver requested SRB extensions when it initialized. If a miniport driver controls an application-dedicated HBA so that it supports this request, the miniport driver should execute the request and notify the operating system-specific port driver when the SRB has completed, using the normal mechanism of calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportnotification">StorPortNotification</a> with <b>RequestComplete</b> and <b>NextRequest</b>.


##### - SrbFunction.SRB_FUNCTION_LOCK_QUEUE (0x18)

Holds requests that are queued by the port driver for a particular logical unit, typically while a power request is being processed. Only the SRB <b>Length</b>, <b>Function</b>, <b>SrbFlags</b>, and <b>OriginalRequest</b> members are valid. When the queue is locked, only requests with <b>SrbFlags</b> ORed with <b>SRB_FLAGS_BYPASS_LOCKED_QUEUE</b> will be processed. SCSI miniport drivers do not process <b>SRB_FUNCTION_LOCK_QUEUE</b> requests. 


##### - SrbFunction.SRB_FUNCTION_PNP (0x25)

The request is a PnP extended request formatted as a <b>SRBEX_DATA_PNP</b> structure. The offset to extended request data is located at <b>SrbExDataOffset</b>[0].


##### - SrbFunction.SRB_FUNCTION_POWER (0x24)

The request is a power extended request formatted as a <b>SRBEX_DATA_POWER</b> structure. The offset to extended request data is located at <b>SrbExDataOffset</b>[0].


##### - SrbFunction.SRB_FUNCTION_QUIESCE_DEVICE (0x1A)

The request is only between a storage class and storage port driver and is not be sent to miniport. The this function serves as a wait by the class driver for port driver to complete all outstanding I/Os.


##### - SrbFunction.SRB_FUNCTION_RECEIVE_EVENT (0x03)

The HBA should be prepared to receive an asynchronous event notification from the addressed target. The SRB <b>DataBuffer</b> member indicates where the data should be placed.

<div class="alert"><b>Note</b>  This function is not sent to the miniport by Storport.</div>
<div> </div>

##### - SrbFunction.SRB_FUNCTION_RELEASE_RECOVERY (0x11)

A SCSIMESS_RELEASE_RECOVERY message should be sent to the target controller. Extended SRB data is not required for this function.

<div class="alert"><b>Note</b>  This function is not sent to the miniport by Storport.</div>
<div> </div>

##### - SrbFunction.SRB_FUNCTION_RESET_BUS (0x12)

The SCSI bus should be reset using the SCSIMESS_BUS_DEVICE_RESET message. A miniport driver receives this request only if a given request has timed out and a subsequent request to abort the timed-out request also has timed out. Extended SRB data is not required for this function.


##### - SrbFunction.SRB_FUNCTION_RESET_DEVICE (0x16)

 The SCSI target controller should be reset using the SCSIMESS_BUS_DEVICE_RESET message. The miniport driver should complete any active requests for the target controller. Extended SRB data is not required for this function.


##### - SrbFunction.SRB_FUNCTION_RESET_LOGICAL_UNIT (0x20)

The logical unit should be reset, if possible. The HBA miniport driver should complete any active requests for the logical unit. Extended SRB data is not required for this function. Storport supports this type of reset, but SCSI port does not. 


##### - SrbFunction.SRB_FUNCTION_SHUTDOWN (0x07)

The system is being shut down. A miniport driver can receive several of these notifications before all system activity actually stops. However, the last shutdown notification will occur after the last start I/O. Extended SRB data is not required for this function.


##### - SrbFunction.SRB_FUNCTION_TERMINATE_IO (0x14)

A SCSIMESS_TERMINATE_IO_PROCESS message should be sent to cancel the request pointed to by the <b>NextSrb</b> member. If the indicated request has already completed, this request should be completed normally. Extended SRB data is not required for this function.

<div class="alert"><b>Note</b>  This function is not sent to the miniport by Storport.</div>
<div> </div>

##### - SrbFunction.SRB_FUNCTION_UNLOCK_QUEUE (0x19)

Releases the port driver's queue for a logical unit that was previously locked with <b>SRB_FUNCTION_LOCK_QUEUE</b>. The <b>SrbFlags</b> of the unlock request must be ORed with <b>SRB_FLAGS_BYPASS_LOCKED_QUEUE</b>. Only the SRB <b>Length</b>, <b>Function</b>, <b>SrbFlags</b>, and <b>OriginalRequest</b> members are valid. SCSI miniport drivers do not process <b>SRB_FUNCTION_UNLOCK_QUEUE</b> requests.


##### - SrbFunction.SRB_FUNCTION_WMI (0x17)

The request is a power extended request formatted as a <b>SRBEX_DATA_WMI</b> structure. The offset to extended request data is located at <b>SrbExDataOffset</b>[0].


##### - SrbStatus.SRB_STATUS_ABORTED

Indicates the request was aborted as directed by the port driver. A miniport driver sets this status in the <b>NextSrb</b> member for a successful SRB_FUNCTION_ABORT_COMMAND request.


##### - SrbStatus.SRB_STATUS_ABORT_FAILED

Indicates an attempt to abort the request failed. Return this status for an SRB_FUNCTION_ABORT_COMMAND request when the specified request cannot be located.


##### - SrbStatus.SRB_STATUS_AUTOSENSE_VALID

Indicates information returned in the <b>SenseInfoBuffer</b> is valid.


##### - SrbStatus.SRB_STATUS_BAD_FUNCTION

Indicates the SRB <b>Function</b> code is not supported.


##### - SrbStatus.SRB_STATUS_BAD_SRB_BLOCK_LENGTH

Indicates the request failed because SRB length was invalid.


##### - SrbStatus.SRB_STATUS_BUSY

Indicates the miniport driver or target device could not accept the request at this time. The operating system-specific port driver will resubmit the request later.


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

Indicates that the Storport driver could not deliver the request to the miniport driver or target device. In such cases, status is recorded in <b>InternalStatus</b>.


##### - SrbStatus.SRB_STATUS_INVALID_LUN

Indicates the <b>Lun</b> value in the SRB is invalid.


##### - SrbStatus.SRB_STATUS_INVALID_PATH_ID

Indicates the <b>PathId</b> specified in the SRB does not exist.


##### - SrbStatus.SRB_STATUS_INVALID_REQUEST

Indicates the miniport driver does not support the given request.


##### - SrbStatus.SRB_STATUS_INVALID_TARGET_ID

Indicates the <b>TargetID</b> value in the SRB is invalid.


##### - SrbStatus.SRB_STATUS_LINK_DOWN

Indicates the request failed because link is down.


##### - SrbStatus.SRB_STATUS_MESSAGE_REJECTED

Indicates the target rejected a message. This is normally returned only for such message-type requests as SRB_FUNCTION_TERMINATE_IO.


##### - SrbStatus.SRB_STATUS_NOT_POWERED

A indicates the request failed because the target is not powered. For requests with SRB_FLAGS_NO_KEEP_AWAKE set in <b>SrbFlags</b>, requests sent to LUNs that are powered down will fail with this status.


##### - SrbStatus.SRB_STATUS_NO_DEVICE

Indicates the device did not respond.


##### - SrbStatus.SRB_STATUS_NO_HBA

Indicates the HBA does not respond.


##### - SrbStatus.SRB_STATUS_PARITY_ERROR

Indicates a parity error occurred on the SCSI bus and that a retry failed.


##### - SrbStatus.SRB_STATUS_PENDING

Indicates the request is in progress. The operating system-specific port driver initializes <b>SrbStatus</b> to this value.


##### - SrbStatus.SRB_STATUS_PHASE_SEQUENCE_FAILURE

Indicates the HBA detected an illegal phase sequence failure error.


##### - SrbStatus.SRB_STATUS_QUEUE_FROZEN

A miniport driver should never set the <b>SrbStatus</b> member to this value. The Windows  port driver can set this value to inform a storage class driver that its queue of requests for a particular peripheral has been frozen. 


##### - SrbStatus.SRB_STATUS_REQUEST_FLUSHED

Indicates the request for status was stopped.


##### - SrbStatus.SRB_STATUS_REQUEST_SENSE_FAILED

Indicates the request-sense command failed. This is returned only if the host bus adapter (HBA) performs auto request sense and the miniport driver set <b>AutoRequestSense</b> to <b>TRUE</b> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> for this HBA.


##### - SrbStatus.SRB_STATUS_SELECTION_TIMEOUT

Indicates the SCSI device selection timed out.


##### - SrbStatus.SRB_STATUS_SUCCESS

Indicates the request was completed successfully.


##### - SrbStatus.SRB_STATUS_TIMEOUT

Indicates the request timed out.


##### - SrbStatus.SRB_STATUS_UNEXPECTED_BUS_FREE

Indicates the target disconnected unexpectedly.


## -remarks



Starting in Windows 8, an extended  SRB type is supported with the use of the <b>STORAGE_REQUEST_BLOCK</b> structure. <b>STORAGE_REQUEST_BLOCK</b> extends SRB functions, allowing extended data blocks for the SRB function to be added to the request. Support for SRB requests using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a> structure will continue.

If <b>NumSrbExData</b> > 0, the offsets for the SRB extended data blocks are in the  <b>SrbExDataOffset</b> array. Each offset is relative to the beginning of this structure and points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_srbex_data">SRBEX_DATA</a> structure containing the extended data block.

The target device address for the SRB is in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-_stor_address">STOR_ADDRESS</a> structure indicated by <b>AddressOffset</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-_stor_address">STOR_ADDRESS</a>
 

 

