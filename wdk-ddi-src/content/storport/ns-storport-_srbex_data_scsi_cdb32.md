---
UID: NS:storport._SRBEX_DATA_SCSI_CDB32
title: "_SRBEX_DATA_SCSI_CDB32"
author: windows-driver-content
description: The SRBEX_DATA_SCSI_CDB32 structure contains the extended SRB data for a 32-byte SCSI command data block (CDB).
old-location: storage\srbex_data_scsi_cdb32.htm
old-project: storage
ms.assetid: 8BE53883-2FD0-4CAB-928E-532587DA80C3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/PSRBEX_DATA_SCSI_CDB32, _SRBEX_DATA_SCSI_CDB32, storport/SRBEX_DATA_SCSI_CDB32, SRBEX_DATA_SCSI_CDB32 structure [Storage Devices], storage.srbex_data_scsi_cdb32, PSRBEX_DATA_SCSI_CDB32 structure pointer [Storage Devices], SRBEX_DATA_SCSI_CDB32, PSRBEX_DATA_SCSI_CDB32, *PSRBEX_DATA_SCSI_CDB32
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h, Srb.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Storport.h
apiname:
-	SRBEX_DATA_SCSI_CDB32
product: Windows
targetos: Windows
req.typenames: SRBEX_DATA_SCSI_CDB32, *PSRBEX_DATA_SCSI_CDB32
req.product: Windows 10 or later.
---

# _SRBEX_DATA_SCSI_CDB32 structure


## -description


The <b>SRBEX_DATA_SCSI_CDB32</b> structure contains the extended SRB data for a 32-byte SCSI command data block (CDB).
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _SRBEX_DATA_SCSI_CDB32 {
  SRBEXDATATYPE       Type;
  ULONG               Length;
  UCHAR               ScsiStatus;
  UCHAR               SenseInfoBufferLength;
  ULONG               CdbLength;
  UCHAR               Reserved;
  ULONG               Reserved1;
  PVOID POINTER_ALIGN SenseInfoBuffer;
  UCHAR POINTER_ALIGN Cdb[32];
} SRBEX_DATA_SCSI_CDB32, *PSRBEX_DATA_SCSI_CDB32;
````


## -struct-fields




### -field Type

Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypeScsiCdb32</b>.


### -field Length

Length of the data in this structure starting with the <b>ScsiStatus</b> member. Set to SRBEX_DATA_SCSI_CDB32_LENGTH.


### -field ScsiStatus

The SCSI status code returned for the submitted SRB.


### -field SenseInfoBufferLength

The length of the sense information returned in the buffer pointed to by <b>SenseInfoBuffer</b>.


### -field CdbLength

The length of the CDB data, in bytes, of the <b>Cdb</b> array.


### -field Reserved

This member is reserved. Set to 0.


### -field Reserved1

This member is reserved. Set to 0.


### -field SenseInfoBuffer

A pointer to a buffer containing any returned sense information.


### -field Cdb

The 32-byte CDB buffer.


## -remarks



This structure is used to submit an extended SRB data for a CDB of 32 bytes or less.




## -see-also

<a href="..\srb\ns-srb-_srbex_data_scsi_cdb16.md">SRBEX_DATA_SCSI_CDB16</a>



<a href="..\srb\ns-srb-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SRBEX_DATA_SCSI_CDB32 structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

