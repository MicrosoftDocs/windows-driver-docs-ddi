---
UID: NS:storport._STORAGE_REQUEST_BLOCK
title: _STORAGE_REQUEST_BLOCK
author: windows-driver-content
description: The STORAGE_REQUEST_BLOCK is the extended format SCSI Request Block (SRB) structure.
old-location: storage\storage_request_block.htm
old-project: storage
ms.assetid: 67A5077D-B1AD-49B7-B024-D139E375483F
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STORAGE_REQUEST_BLOCK, STORAGE_REQUEST_BLOCK, PSTORAGE_REQUEST_BLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h, Srb.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_REQUEST_BLOCK
req.alt-loc: Storport.h
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
req.typenames: STORAGE_REQUEST_BLOCK, PSTORAGE_REQUEST_BLOCK
req.product: Windows 10 or later.
---

# _STORAGE_REQUEST_BLOCK structure



## -description

   The <b>STORAGE_REQUEST_BLOCK</b> is the extended format SCSI Request Block (SRB) structure. The structure provides for the addition of extended data associated with an SRB function.



## -syntax

````
typedef struct _STORAGE_REQUEST_BLOCK {
  USHORT                        Length;
  UCHAR                         Function;
  UCHAR                         SrbStatus;
  UCHAR                         ReservedUchar[4];
  ULONG                         Signature;
  ULONG                         Version;
  ULONG                         SrbLength;
  ULONG                         SrbFunction;
  ULONG                         SrbFlags;
  ULONG                         ReservedUlong;
  ULONG                         RequestTag;
  USHORT                        RequestPriority;
  USHORT                        RequestAttribute;
  ULONG                         TimeOutValue;
  ULONG                         SystemStatus;
  ULONG                         ZeroGuard1;
  ULONG                         AddressOffset;
  ULONG                         NumSrbExData;
  ULONG                         DataTransferLength;
  PVOID                         DataBuffer;
  PVOID                         ZeroGuard2;
  PVOID                         OriginalRequest;
  PVOID                         ClassContext;
  PVOID                         PortContext;
  PVOID                         MiniportContext;
  struct _STORAGE_REQUEST_BLOCK  *NextSrb;
  ULONG                         SrbExDataOffset[ANYSIZE_ARRAY];
} STORAGE_REQUEST_BLOCK, *PSTORAGE_REQUEST_BLOCK;
````


## -struct-fields

### -field Length

Specifies the size of the SRB header for compatibility with the <a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a> structure. This is equal to the offset of the <b>Signature</b> member of this structure.


### -field Function

Set to <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b> to indicate that this is an extended SRB. Unlike in <a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>, the SRB function identifier is in the <b>SrbFunction</b> member instead.


### -field SrbStatus

Returns the status of the completed request. This member should be set by the miniport driver before it notifies the operating system-specific driver that the request has completed by calling <a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a> with <b>RequestComplete</b>. The value of this member can be one of the following:


### -field SRB_STATUS_PENDING

<dd>
Indicates the request is in progress. The operating system-specific port driver initializes <b>SrbStatus</b> to this value.


### -field SRB_STATUS_SUCCESS

<dd>
Indicates the request was completed successfully.


### -field SRB_STATUS_ABORTED

<dd>
Indicates the request was aborted as directed by the port driver. A miniport driver sets this status in the <b>NextSrb</b> member for a successful SRB_FUNCTION_ABORT_COMMAND request.


### -field SRB_STATUS_ABORT_FAILED

<dd>
Indicates an attempt to abort the request failed. Return this status for an SRB_FUNCTION_ABORT_COMMAND request when the specified request cannot be located.


### -field SRB_STATUS_ERROR

<dd>
Indicates the request was completed with an error in the SCSI bus status.


### -field SRB_STATUS_BUSY

<dd>
Indicates the miniport driver or target device could not accept the request at this time. The operating system-specific port driver will resubmit the request later.


### -field SRB_STATUS_INTERNAL_ERROR

<dd>
Indicates that the Storport driver could not deliver the request to the miniport driver or target device. In such cases, status is recorded in <b>InternalStatus</b>.


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
Indicates the request-sense command failed. This is returned only if the host bus adapter (HBA) performs auto request sense and the miniport driver set <b>AutoRequestSense</b> to <b>TRUE</b> in the <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> for this HBA.


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
A miniport driver should never set the <b>SrbStatus</b> member to this value. The Windows  port driver can set this value to inform a storage class driver that its queue of requests for a particular peripheral has been frozen. 


### -field SRB_STATUS_NOT_POWERED

<dd>
A indicates the request failed because the target is not powered. For requests with SRB_FLAGS_NO_KEEP_AWAKE set in <b>SrbFlags</b>, requests sent to LUNs that are powered down will fail with this status.


### -field SRB_STATUS_LINK_DOWN

<dd>
Indicates the request failed because link is down.


### -field SRB_STATUS_BAD_SRB_BLOCK_LENGTH

<dd>
Indicates the request failed because SRB length was invalid.

</dd>
</dl>

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


### -field SRB_FUNCTION_EXECUTE_SCSI (0x00)

<dd>
A SCSI device I/O request should be executed on the target logical unit. When <b>NumSrbExData</b> &gt; 0, one or more following extended request block structures are located at the offsets specified in <b>SrbExDataOffset</b>.

<dl>
<dd>
<a href="..\srb\ns-srb-_srbex_data_scsi_cdb16.md">SRBEX_DATA_SCSI_CDB16</a>
</dd>
<dd>
<a href="..\srb\ns-srb-_srbex_data_scsi_cdb32.md">SRBEX_DATA_SCSI_CDB32</a>
</dd>
<dd>
<a href="..\srb\ns-srb-_srbex_data_scsi_cdb_var.md">SRBEX_DATA_SCSI_CDB_VAR</a>
</dd>
<dd>
<a href="..\srb\ns-srb-_srbex_data_bidirectional.md">SRBEX_DATA_BIDIRECTIONAL</a> (when <b>Cdb</b> is bi-directional)</dd>
<dd>
<a href="..\srb\ns-srb-_srbex_data_io_info.md">SRBEX_DATA_IO_INFO</a> (when <b>Cdb</b> is read or write)</dd>
</dl>

### -field SRB_FUNCTION_ABORT_COMMAND (0x10)

<dd>
A SCSIMESS_ABORT message should be sent to cancel the request pointed to by the <b>NextSrb</b> member. If this is a tagged-queue request, a SCSIMESS_ABORT_WITH_TAG message should be used instead. If the indicated request has been completed, this request should be completed normally. Extended SRB data is not required for this function.

<div class="alert"><b>Note</b>  This function is not sent to the miniport by Storport.</div>
<div> </div>

### -field SRB_FUNCTION_RESET_DEVICE (0x16)

<dd>
 The SCSI target controller should be reset using the SCSIMESS_BUS_DEVICE_RESET message. The miniport driver should complete any active requests for the target controller. Extended SRB data is not required for this function.


### -field SRB_FUNCTION_RESET_LOGICAL_UNIT (0x20)

<dd>
The logical unit should be reset, if possible. The HBA miniport driver should complete any active requests for the logical unit. Extended SRB data is not required for this function. Storport supports this type of reset, but SCSI port does not. 


### -field SRB_FUNCTION_RESET_BUS (0x12)

<dd>
The SCSI bus should be reset using the SCSIMESS_BUS_DEVICE_RESET message. A miniport driver receives this request only if a given request has timed out and a subsequent request to abort the timed-out request also has timed out. Extended SRB data is not required for this function.


### -field SRB_FUNCTION_TERMINATE_IO (0x14)

<dd>
A SCSIMESS_TERMINATE_IO_PROCESS message should be sent to cancel the request pointed to by the <b>NextSrb</b> member. If the indicated request has already completed, this request should be completed normally. Extended SRB data is not required for this function.

<div class="alert"><b>Note</b>  This function is not sent to the miniport by Storport.</div>
<div> </div>

### -field SRB_FUNCTION_RELEASE_RECOVERY (0x11)

<dd>
A SCSIMESS_RELEASE_RECOVERY message should be sent to the target controller. Extended SRB data is not required for this function.

<div class="alert"><b>Note</b>  This function is not sent to the miniport by Storport.</div>
<div> </div>

### -field SRB_FUNCTION_RECEIVE_EVENT (0x03)

<dd>
The HBA should be prepared to receive an asynchronous event notification from the addressed target. The SRB <b>DataBuffer</b> member indicates where the data should be placed.

<div class="alert"><b>Note</b>  This function is not sent to the miniport by Storport.</div>
<div> </div>

### -field SRB_FUNCTION_SHUTDOWN (0x07)

<dd>
The system is being shut down. A miniport driver can receive several of these notifications before all system activity actually stops. However, the last shutdown notification will occur after the last start I/O. Extended SRB data is not required for this function.


### -field SRB_FUNCTION_FLUSH (0x08)

<dd>
The miniport driver should flush any cached data for the target device. This request is sent to the miniport driver only if it set <b>CachesData</b> to <b>TRUE</b> in the <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> for the HBA. Extended SRB data is not required for this function.


### -field SRB_FUNCTION_IO_CONTROL (0x02)

<dd>
The request is an I/O control request, originating in a user-mode application with a dedicated HBA. The SRB <b>DataBuffer</b> points to an <b>SRB_IO_CONTROL</b> header followed by the data area. The value in <b>DataBuffer</b> can be used by the driver, regardless of the value of <b>MapBuffers</b>. Only the SRB <b>Function</b>, <b>SrbFlags</b>, <b>TimeOutValue</b>, <b>DataBuffer</b>, and <b>DataTransferLength</b> members are valid, along with the <b>SrbExtension</b> member if the miniport driver requested SRB extensions when it initialized. If a miniport driver controls an application-dedicated HBA so that it supports this request, the miniport driver should execute the request and notify the operating system-specific port driver when the SRB has completed, using the normal mechanism of calls to <a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a> with <b>RequestComplete</b> and <b>NextRequest</b>.


### -field SRB_FUNCTION_LOCK_QUEUE (0x18)

<dd>
Holds requests that are queued by the port driver for a particular logical unit, typically while a power request is being processed. Only the SRB <b>Length</b>, <b>Function</b>, <b>SrbFlags</b>, and <b>OriginalRequest</b> members are valid. When the queue is locked, only requests with <b>SrbFlags</b> ORed with <b>SRB_FLAGS_BYPASS_LOCKED_QUEUE</b> will be processed. SCSI miniport drivers do not process <b>SRB_FUNCTION_LOCK_QUEUE</b> requests. 


### -field SRB_FUNCTION_UNLOCK_QUEUE (0x19)

<dd>
Releases the port driver's queue for a logical unit that was previously locked with <b>SRB_FUNCTION_LOCK_QUEUE</b>. The <b>SrbFlags</b> of the unlock request must be ORed with <b>SRB_FLAGS_BYPASS_LOCKED_QUEUE</b>. Only the SRB <b>Length</b>, <b>Function</b>, <b>SrbFlags</b>, and <b>OriginalRequest</b> members are valid. SCSI miniport drivers do not process <b>SRB_FUNCTION_UNLOCK_QUEUE</b> requests.


### -field SRB_FUNCTION_DUMP_POINTERS (0x26)

<dd>
A request with this function is sent to a Storport miniport driver that is used to control the disk that holds the crash dump data. The request collects information needed from the miniport driver to support crash dump and hibernation. See the <b>MINIPORT_DUMP_POINTERS</b> structure. A physical miniport driver must set the STOR_FEATURE_DUMP_POINTERS flag in the <b>FeatureSupport</b> member of its <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> to receive a request with this function.


### -field SRB_FUNCTION_FREE_DUMP_POINTERS (0x27)

<dd>
A request with this function is sent to a Storport miniport driver to release any resources allocated during a previous request for SRB_FUNCTION_DUMP_POINTERS.


### -field SRB_FUNCTION_QUIESCE_DEVICE (0x1A)

<dd>
The request is only between a storage class and storage port driver and is not be sent to miniport. The this function serves as a wait by the class driver for port driver to complete all outstanding I/Os.


### -field SRB_FUNCTION_PNP (0x25)

<dd>
The request is a PnP extended request formatted as a <b>SRBEX_DATA_PNP</b> structure. The offset to extended request data is located at <b>SrbExDataOffset</b>[0].


### -field SRB_FUNCTION_POWER (0x24)

<dd>
The request is a power extended request formatted as a <b>SRBEX_DATA_POWER</b> structure. The offset to extended request data is located at <b>SrbExDataOffset</b>[0].


### -field SRB_FUNCTION_WMI (0x17)

<dd>
The request is a power extended request formatted as a <b>SRBEX_DATA_WMI</b> structure. The offset to extended request data is located at <b>SrbExDataOffset</b>[0].


### -field SRB_FUNCTION_CRYPTO_OPERATION ()

<dd>
Reserved for system use.

</dd>
</dl>

### -field SrbFlags

Indicates various parameters and options for the request. <b>SrbFlags</b> is read-only, except when <b>SRB_FLAGS_UNSPECIFIED_DIRECTION</b> is set and miniport drivers of subordinate DMA adapters are required to update <b>SRB_FLAGS_DATA_IN</b> or <b>SRB_FLAGS_DATA_OUT</b>. This member can have one or more of these flags set:


### -field SRB_FLAGS_QUEUE_ACTION_ENABLE

<dd>
Indicates tagged-queue actions are to be enabled.


### -field SRB_FLAGS_DISABLE_AUTOSENSE

<dd>
Indicates request-sense information should not be returned.


### -field SRB_FLAGS_DATA_IN

<dd>
Indicates data will be transferred from the device to the system.


### -field SRB_FLAGS_DATA_OUT

<dd>
Indicates data will be transferred from the system to the device.


### -field SRB_FLAGS_UNSPECIFIED_DIRECTION

<dd>
Defined for backward compatibility with the ASPI/CAM SCSI interfaces, this flag indicates that the transfer direction could be either of the preceding, because both of the preceding flags are set. If this flag is set, a miniport driver should determine the transfer direction by examining the data phase for the target on the SCSI bus.


### -field SRB_FLAGS_NO_DATA_TRANSFER

<dd>
Indicates no data transfer with this request. If this is set, the flags <b>SRB_FLAGS_DATA_OUT</b>, <b>SRB_FLAGS_DATA_IN</b>, and <b>SRB_FLAGS_UNSPECIFIED_DIRECTION</b> are clear.


### -field SRB_FLAGS_DISABLE_SYNCH_TRANSFER

<dd>
Indicates the HBA, if possible, should perform asynchronous I/O for this transfer request. If synchronous I/O was negotiated previously, the HBA must renegotiate for asynchronous I/O before performing the transfer.


### -field SRB_FLAGS_DISABLE_DISCONNECT

<dd>
Indicates the HBA should not allow the target to disconnect from the SCSI bus during processing of this request.


### -field SRB_FLAGS_BYPASS_FROZEN_QUEUE

<dd>
This flag is irrelevant to miniport drivers.


### -field SRB_FLAGS_NO_QUEUE_FREEZE

<dd>
This flag is irrelevant to miniport drivers.


### -field SRB_FLAGS_IS_ACTIVE

<dd>
This flag is irrelevant to miniport drivers.


### -field SRB_FLAGS_ALLOCATED_FROM_ZONE

<dd>
This flag is irrelevant to miniport drivers and is obsolete to new Windows class drivers. To a Windows legacy class driver, this indicates whether the SRB was allocated from a zone buffer. If this flag is set, the class driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545387">ExInterlockedFreeToZone</a> to release the SRB; otherwise, it must call <a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>. New class drivers should use lookaside lists rather than zone buffers.


### -field SRB_FLAGS_SGLIST_FROM_POOL

<dd>
This flag is irrelevant to miniport drivers. To the class driver, this indicates that memory for a scatter/gather list was allocated from a nonpaged pool. If this flag is set, the class driver must call <a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a> to release the memory after the SRB is completed. 


### -field SRB_FLAGS_BYPASS_LOCKED_QUEUE

<dd>
This flag is irrelevant to miniport drivers. To the port driver, this flag indicates that the request should be processed whether the logical-unit queue is locked or not. A higher-level driver must set this flag to send an <b>SRB_FUNCTION_UNLOCK_QUEUE</b> request.


### -field SRB_FLAGS_NO_KEEP_AWAKE

<dd>
This flag is irrelevant to miniport drivers. A Windows class driver uses this flag to indicate to the port driver to fail the request rather than powering up the device to handle this request.


### -field SRB_FLAGS_FREE_SENSE_BUFFER

<dd>
Indicates that either the port or the miniport driver has allocated a buffer for sense data. This informs the class driver that it must free the sense data buffer after extracting the data.


### -field SRB_FLAGS_D3_PROCESSING

<dd>
Indicates that the request is part of D3 processing. Miniports that support runtime power control should not call <b>StorPortPoFxActivateComponent</b> or <b>StorPortPoFxIdleComponent</b> with these requests


### -field SRB_FLAGS_ADAPTER_CACHE_ENABLE

<dd>
Indicates that the adapter can cache data.

</dd>
</dl>

### -field ReservedUlong

Reserved. Set to 0.


### -field RequestTag

Contains the queue-tag value assigned by the operating system-specific port driver. If this member is used for tagged queuing, the HBA supports internal queuing of requests to logical units (LUs) and the miniport driver set <b>TaggedQueueing</b> to <b>TRUE</b> in the PORT_CONFIGURATION_INFORMATION for this HBA.


### -field RequestPriority

The priority assignment for the SRB.


### -field RequestAttribute

Indicates the tagged-queuing message to be used when the <b>SRB_FLAGS_QUEUE_ACTION_ENABLE</b> flag is set. The value can be one of the following: <b>SRB_SIMPLE_TAG_REQUEST</b>, <b>SRB_HEAD_OF_QUEUE_TAG_REQUEST</b>, or <b>SRB_ORDERED_QUEUE_TAG_REQUEST</b>.


### -field TimeOutValue

Indicates the interval, in seconds, that the request can execute before the operating system-specific port driver might consider it timed out. Miniport drivers are not required to time requests because the port driver already does.


### -field SystemStatus

Used by the Storport driver, instead of <b>SrbStatus</b>, to report the status of the completed request whenever the request cannot be delivered to the miniport driver. In such cases, <b>SrbStatus</b> is set to <b>SRB_STATUS_INTERNAL_ERROR</b>. This member is used exclusively for communication between the Storport and the class driver and should not be used by miniport drivers.


### -field ZeroGuard1

A guard area to protect against drivers that interpret this structure as <a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>. Set to 0.


### -field AddressOffset

The offset of the storage request address from the beginning of this structure. This offset locates a <a href="..\scsi\ns-scsi-_stor_address.md">STOR_ADDRESS</a> structure that contains the address for the request.


### -field NumSrbExData

The count of extended SRB data blocks for this request.


### -field DataTransferLength

Indicates the size, in bytes, of the data buffer. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred.


### -field DataBuffer

Points to the data buffer. Miniport drivers should not use this value as a data pointer unless the miniport driver set <b>MapBuffers</b> to <b>TRUE</b> in the <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> for the HBA. In the case of SRB_FUNCTION_IO_CONTROL requests, however, miniport drivers can use this value as a data pointer regardless of the value of <b>MapBuffers</b>.


### -field ZeroGuard2

A guard area to protect against drivers that interpret this structure as <a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>. Set to 0.


### -field OriginalRequest

Points to the IRP for this request. This member is irrelevant to miniport drivers.


### -field ClassContext

Points to a class driver context data for this request. This member is irrelevant to miniport drivers.


### -field PortContext

Points to a port driver context data for this request. This member is irrelevant to miniport drivers.


### -field MiniportContext

Points to the Srb extension. A miniport driver must not use this member if it set <b>SrbExtensionSize</b> to zero in  <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a>. The memory at <b>MiniportContext</b> is not initialized by the operating system-specific port driver, and the miniport driver-determined data can be accessed directly by the HBA. The corresponding physical address can be obtained by calling <a href="..\storport\nf-storport-storportgetphysicaladdress.md">StorportGetPhysicalAddress</a> with the <b>MiniportContext</b> pointer.


### -field NextSrb

Indicates the <b>STORAGE_REQUEST_BLOCK</b> to which this request applies. Only a small subset of requests use a second SRB, for example SRB_FUNCTION_ABORT_COMMAND.


### -field SrbExDataOffset

An array of offsets specifying the location of extended data blocks for the SRB. This array is empty if <b>NumSrbExData</b> = 0.


## -remarks
Starting in Windows 8, an extended  SRB type is supported with the use of the <b>STORAGE_REQUEST_BLOCK</b> structure. <b>STORAGE_REQUEST_BLOCK</b> extends SRB functions, allowing extended data blocks for the SRB function to be added to the request. Support for SRB requests using the <a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a> structure will continue.

If <b>NumSrbExData</b> &gt; 0, the offsets for the SRB extended data blocks are in the  <b>SrbExDataOffset</b> array. Each offset is relative to the beginning of this structure and points to a <a href="..\srb\ns-srb-_srbex_data.md">SRBEX_DATA</a> structure containing the extended data block.

The target device address for the SRB is in a <a href="..\scsi\ns-scsi-_stor_address.md">STOR_ADDRESS</a> structure indicated by <b>AddressOffset</b>.


## -see-also
<dl>
<dt>
<a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="..\scsi\ns-scsi-_stor_address.md">STOR_ADDRESS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_REQUEST_BLOCK structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

