---
UID: NS:ntddscsi._SRB_IO_CONTROL
title: "_SRB_IO_CONTROL"
author: windows-driver-content
description: SRB_IO_CONTROL structure
old-location: storage\srb_io_control.htm
old-project: storage
ms.assetid: 754d2a4c-6a22-4c25-87e2-e30e87b9c1ba
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSRB_IO_CONTROL, PSRB_IO_CONTROL, PSRB_IO_CONTROL structure pointer [Storage Devices], SRB_IO_CONTROL, SRB_IO_CONTROL structure [Storage Devices], _SRB_IO_CONTROL, ntddscsi/PSRB_IO_CONTROL, ntddscsi/SRB_IO_CONTROL, storage.srb_io_control, structs-scsibus_d7cd0432-d4be-4609-a3f9-91ef842caf7e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddscsi.h
apiname:
-	SRB_IO_CONTROL
product: Windows
targetos: Windows
req.typenames: SRB_IO_CONTROL, *PSRB_IO_CONTROL
---

# _SRB_IO_CONTROL structure


## -description


<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _SRB_IO_CONTROL {
  ULONG HeaderLength;
  UCHAR Signature[8];
  ULONG Timeout;
  ULONG ControlCode;
  ULONG ReturnCode;
  ULONG Length;
} SRB_IO_CONTROL, *PSRB_IO_CONTROL;
````


## -struct-fields




### -field HeaderLength

Is <b>sizeof</b>(SRB_IO_CONTROL).


### -field Signature

Identifies the application-dedicated, target HBA for this request. This signature is used to prevent conflicts in <b>ControlCode</b> values between vendors. It should be a string of ASCII characters. If a miniport driver does not recognize the input <b>Signature</b> value, it must complete the request with a status of SRB_STATUS_INVALID_REQUEST.


### -field Timeout

Indicates the interval in seconds that the request can execute before the OS-specific port driver might consider it timed out. Miniport drivers should be enforcing timeouts for SRB_IO_CONTROL, especially for any privately defined SRB_IO_CONTROL.


### -field ControlCode

Indicates the operation to be performed. There are no system-defined operations. Values must be defined by the driver as a set of private I/O control codes with which the application can make requests by calling the Win32 <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> function. For more information about defining private I/O control codes for device control requests, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565406">Using I/O Control Codes</a>.


### -field ReturnCode

Returns a status code for examination by the requesting application.


### -field Length

Indicates the size in bytes of the immediately following data area. This area can be divided for the particular operation into input and output areas. For input requests, the contents of the DataBuffer will be copied to the requester up to the returned value of DataTransferLength.


## -remarks



This structure is used by applications to send requests directly to an application-dedicated HBA. Note that such an application also must set up requests to program its dedicated HBA.




## -see-also

<a href="..\storport\ns-storport-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>



SCSI Port I/O Control Codes



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SRB_IO_CONTROL structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

