---
UID: NS:srb._SCSI_WMI_REQUEST_BLOCK
title: _SCSI_WMI_REQUEST_BLOCK (srb.h)
description: This structure is a special version of a SCSI_REQUEST_BLOCK for use with WMI commands.
old-location: storage\scsi_wmi_request_block.htm
tech.root: storage
ms.assetid: 6dc10c3a-b47e-42c3-a209-34977fb219f1
ms.date: 03/29/2018
keywords: ["_SCSI_WMI_REQUEST_BLOCK structure"]
ms.keywords: "*PSCSI_WMI_REQUEST_BLOCK, PSCSI_WMI_REQUEST_BLOCK, PSCSI_WMI_REQUEST_BLOCK structure pointer [Storage Devices], SCSI_WMI_REQUEST_BLOCK, SCSI_WMI_REQUEST_BLOCK structure [Storage Devices], _SCSI_WMI_REQUEST_BLOCK, srb/PSCSI_WMI_REQUEST_BLOCK, srb/SCSI_WMI_REQUEST_BLOCK, storage.scsi_wmi_request_block, structs-scsibus_6188bca6-990b-4471-b8ea-2cd5b2b27d51.xml"
f1_keywords:
 - "srb/SCSI_WMI_REQUEST_BLOCK"
 - "SCSI_WMI_REQUEST_BLOCK"
req.header: srb.h
req.include-header: Storport.h, Srb.h, Storport.h, Minitape.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- srb.h
api_name:
- SCSI_WMI_REQUEST_BLOCK
product:
- Windows
targetos: Windows
req.typenames: SCSI_WMI_REQUEST_BLOCK, *PSCSI_WMI_REQUEST_BLOCK
---

# _SCSI_WMI_REQUEST_BLOCK structure


## -description


This structure is a special version of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a> for use with WMI commands. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Length

Specifies the size in bytes of this structure.


### -field Function

SRB_FUNCTION_WMI, which specifies that the request is a WMI request. If this member is not set to SRB_FUNCTION_WMI, the miniport driver should fail the request.


### -field SrbStatus

Returns the status of the completed request. This member should be set by the miniport driver before it notifies the OS-specific driver that the request has completed by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification</a> with <b>RequestComplete</b>. The value of this member can be any value listed for <b>SrbStatus</b> in SCSI_REQUEST_BLOCK.


### -field WMISubFunction

Indicates the WMI action to be performed. A miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a> with <i>MinorFunction</i> set to this value. The subfunction value corresponds to the WMI minor IRP number that identifies the WMI operation. 


### -field PathId

Indicates the SCSI port or bus for the request. This value is zero-based. If SRB_WMI_FLAGS_ADAPTER_REQUEST is set in <b>WMIFlags</b>, this member is reserved.


### -field TargetId

Indicates the target controller or device on the bus. If SRB_WMI_FLAGS_ADAPTER_REQUEST is set in <b>WMIFlags</b>, this member is reserved.


### -field Lun

Indicates the logical unit number of the device. If SRB_WMI_FLAGS_ADAPTER_REQUEST is set in <b>WMIFlags</b>, this member is reserved.


### -field Reserved1

Reserved for system use and not available for use by miniport drivers.


### -field WMIFlags

Indicates that the WMI request is for the adapter if SRB_WMI_FLAGS_ADAPTER_REQUEST is set and that <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b> are reserved. Otherwise, <b>WMIFlags</b> will be <b>NULL</b>, indicating that the request is for the device specified by <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b>.


### -field Reserved2

Reserved for system use and not available for use by miniport drivers.


### -field SrbFlags

Indicates various parameters and options about the request. <b>SrbFlags</b> is read-only. This member will be set to one or more of the following flags ORed together:





#### SRB_FLAGS_DATA_IN

Indicates data will be transferred from the device to the system.





#### SRB_FLAGS_DATA_OUT

Indicates data will be transferred from the system to the device.





#### SRB_FLAGS_NO_DATA_TRANSFER

Indicates no data transfer with this request. If this is set, the flags SRB_FLAGS_DATA_OUT, SRB_FLAGS_DATA_IN, and SRB_FLAGS_UNSPECIFIED_DIRECTION are clear.





#### SRB_FLAGS_DISABLE_SYNCH_TRANSFER

Indicates the HBA, if possible, should perform asynchronous I/O for this transfer request. If synchronous I/O was negotiated previously, the HBA must renegotiate for asynchronous I/O before performing the transfer.





#### SRB_FLAGS_DISABLE_DISCONNECT

Indicates the HBA should not allow the target to disconnect from the SCSI bus during processing of this request.


### -field DataTransferLength

Indicates the size in bytes of the data buffer. A miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a> with <i>BufferSize</i> set to this value. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred.


### -field TimeOutValue

Indicates the interval in seconds that the request can execute before the OS-specific port driver might consider it timed out. Miniport drivers are not required to time requests because the port driver already does.


### -field DataBuffer

Points to the data buffer. A miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a> with <i>Buffer</i> set to this value. Miniport drivers can use this value as a data pointer regardless of the value of <b>MapBuffers</b> in the PORT_CONFIGURATION_INFORMATION for the HBA. A miniport driver cannot transfer data directly into the buffer using DMA.


### -field DataPath

Specifies the WMI data path for this request. A miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a> with <i>DataPath</i> set to this value. 


### -field Reserved3

Reserved for system use and not available for use by miniport drivers.


### -field OriginalRequest

Points to the IRP for this request. This member is irrelevant to miniport drivers.


### -field SrbExtension

Points to the Srb extension. A miniport driver must not use this member if it set <b>SrbExtensionSize</b> to zero in the HW_INITIALIZATION_DATA. The memory at <b>SrbExtension</b> is not initialized by the OS-specific port driver, and the miniport driver-determined data can be accessed directly by the HBA. The corresponding physical address can be obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetphysicaladdress">ScsiPortGetPhysicalAddress</a> with the <b>SrbExtension</b> pointer.


### -field Reserved4

Reserved for system use and not available for use by miniport drivers.


### -field Reserved6

Reserved for system use and not available for use by miniport drivers. This member is valid starting with Windows Server 2003 with SP1.


### -field Reserved5

Reserved for system use and not available for use by miniport drivers.


##### - SrbFlags.SRB_FLAGS_DATA_IN

Indicates data will be transferred from the device to the system.


##### - SrbFlags.SRB_FLAGS_DATA_OUT

Indicates data will be transferred from the system to the device.


##### - SrbFlags.SRB_FLAGS_DISABLE_DISCONNECT

Indicates the HBA should not allow the target to disconnect from the SCSI bus during processing of this request.


##### - SrbFlags.SRB_FLAGS_DISABLE_SYNCH_TRANSFER

Indicates the HBA, if possible, should perform asynchronous I/O for this transfer request. If synchronous I/O was negotiated previously, the HBA must renegotiate for asynchronous I/O before performing the transfer.


##### - SrbFlags.SRB_FLAGS_NO_DATA_TRANSFER

Indicates no data transfer with this request. If this is set, the flags SRB_FLAGS_DATA_OUT, SRB_FLAGS_DATA_IN, and SRB_FLAGS_UNSPECIFIED_DIRECTION are clear.


## -remarks



Windows NT storage class and filter drivers can send WMI SRBs to the system port driver. The system port driver will handle certain WMI requests on behalf of miniport drivers. If the port driver cannot handle a WMI request, it forwards the request to the miniport driver. 

A miniport driver receives WMI requests from the port driver only if the miniport driver set <b>WmiDataProvider</b> in the PORT_CONFIGURATION_INFORMATION structure. If the miniport driver supports a request, it should process it and complete the request by calling <b>ScsiPortNotification</b> twice, first with <b>RequestComplete</b> and then with <b>NextRequest</b> (or <b>NextLuRequest</b>). 

For information about supporting WMI in miniport drivers, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/implementing-wmi">Windows Management Instrumentation</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_hw_initialization_data">HW_INITIALIZATION_DATA (SCSI)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_port_configuration_information">PORT_CONFIGURATION_INFORMATION (SCSI)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>
 

 

