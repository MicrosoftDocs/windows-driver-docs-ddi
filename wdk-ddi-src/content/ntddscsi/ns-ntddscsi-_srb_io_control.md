---
UID: NS:ntddscsi._SRB_IO_CONTROL
title: _SRB_IO_CONTROL (ntddscsi.h)
description: SRB_IO_CONTROL structure
old-location: storage\srb_io_control.htm
tech.root: storage
ms.assetid: 754d2a4c-6a22-4c25-87e2-e30e87b9c1ba
ms.date: 03/29/2018
keywords: ["SRB_IO_CONTROL structure"]
ms.keywords: "*PSRB_IO_CONTROL, PSRB_IO_CONTROL, PSRB_IO_CONTROL structure pointer [Storage Devices], SRB_IO_CONTROL, SRB_IO_CONTROL structure [Storage Devices], _SRB_IO_CONTROL, ntddscsi/PSRB_IO_CONTROL, ntddscsi/SRB_IO_CONTROL, storage.srb_io_control, structs-scsibus_d7cd0432-d4be-4609-a3f9-91ef842caf7e.xml"
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
targetos: Windows
req.typenames: SRB_IO_CONTROL, *PSRB_IO_CONTROL
f1_keywords:
 - _SRB_IO_CONTROL
 - ntddscsi/_SRB_IO_CONTROL
 - PSRB_IO_CONTROL
 - ntddscsi/PSRB_IO_CONTROL
 - SRB_IO_CONTROL
 - ntddscsi/SRB_IO_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddscsi.h
api_name:
 - SRB_IO_CONTROL
---

# _SRB_IO_CONTROL structure


## -description

<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver-overview">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields

### -field HeaderLength

Is <b>sizeof</b>(SRB_IO_CONTROL).

### -field Signature

Identifies the application-dedicated, target HBA for this request. This signature is used to prevent conflicts in <b>ControlCode</b> values between vendors. It should be a string of ASCII characters. If a miniport driver does not recognize the input <b>Signature</b> value, it must complete the request with a status of SRB_STATUS_INVALID_REQUEST.

### -field Timeout

Indicates the interval in seconds that the request can execute before the OS-specific port driver might consider it timed out. Miniport drivers should be enforcing timeouts for SRB_IO_CONTROL, especially for any privately defined SRB_IO_CONTROL.

### -field ControlCode

Indicates the operation to be performed. There are no system-defined operations. Values must be defined by the driver as a set of private I/O control codes with which the application can make requests by calling the Win32 <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a> function. For more information about defining private I/O control codes for device control requests, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-i-o-control-codes">Using I/O Control Codes</a>.

### -field ReturnCode

Returns a status code for examination by the requesting application.

### -field Length

Indicates the size in bytes of the immediately following data area. This area can be divided for the particular operation into input and output areas. For input requests, the contents of the DataBuffer will be copied to the requester up to the returned value of DataTransferLength.

## -remarks

This structure is used by applications to send requests directly to an application-dedicated HBA. Note that such an application also must set up requests to program its dedicated HBA.

## -see-also

SCSI Port I/O Control Codes



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>

