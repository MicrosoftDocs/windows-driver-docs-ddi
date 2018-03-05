---
UID: NS:storport._SRBEX_DATA_SCSI_CDB_VAR
title: "_SRBEX_DATA_SCSI_CDB_VAR"
author: windows-driver-content
description: The SRBEX_DATA_SCSI_CDB_VAR structure contains the extended SRB data for a variable length SCSI command data block (CDB).
old-location: storage\srbex_data_scsi_cdb_var.htm
old-project: storage
ms.assetid: 8D3BD2E0-02EA-4745-AA1C-86D829E6BA81
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSRBEX_DATA_SCSI_CDB_VAR, PSRBEX_DATA_SCSI_CDB_VAR, PSRBEX_DATA_SCSI_CDB_VAR structure pointer [Storage Devices], SRBEX_DATA_SCSI_CDB_VAR, SRBEX_DATA_SCSI_CDB_VAR structure [Storage Devices], _SRBEX_DATA_SCSI_CDB_VAR, storage.srbex_data_scsi_cdb_var, storport/PSRBEX_DATA_SCSI_CDB_VAR, storport/SRBEX_DATA_SCSI_CDB_VAR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h, Srb.h, Minitape.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Storport.h
api_name:
-	SRBEX_DATA_SCSI_CDB_VAR
product: Windows
targetos: Windows
req.typenames: SRBEX_DATA_SCSI_CDB_VAR, *PSRBEX_DATA_SCSI_CDB_VAR
req.product: Windows 10 or later.
---

# _SRBEX_DATA_SCSI_CDB_VAR structure


## -description


The <b>SRBEX_DATA_SCSI_CDB_VAR</b> structure contains the extended SRB data for a variable length SCSI command data block (CDB).
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _SRBEX_DATA_SCSI_CDB_VAR {
  SRBEXDATATYPE       Type;
  ULONG               Length;
  UCHAR               ScsiStatus;
  UCHAR               SenseInfoBufferLength;
  UCHAR               Reserved[2];
  ULONG               CdbLength;
  ULONG               Reserved1[2];
  PVOID POINTER_ALIGN SenseInfoBuffer;
  UCHAR POINTER_ALIGN Cdb[ANYSIZE_ARRAY];
} SRBEX_DATA_SCSI_CDB_VAR, *PSRBEX_DATA_SCSI_CDB_VAR;
````


## -struct-fields




### -field Type

Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypeScsiCdbVar</b>.


### -field Length

Length of the data in this structure starting with the <b>ScsiStatus</b> member. This value ranges between SRBEX_DATA_SCSI_CDB_VAR_LENGTH_MIN and SRBEX_DATA_SCSI_CDB_VAR_LENGTH_MAX.


### -field ScsiStatus

The SCSI status code returned for the submitted SRB.


### -field SenseInfoBufferLength

The length of the sense information returned in the buffer pointed to by <b>SenseInfoBuffer</b>.


### -field Reserved

This member is reserved. Contains zeros.


### -field CdbLength

The length of the CDB data, in bytes, of the <b>Cdb</b> array.


### -field Reserved1

This member is reserved. Contains zeros.


### -field SenseInfoBuffer

A pointer to a buffer containing any returned sense information.


### -field Cdb

A variable length array containing the CDB buffer.


## -remarks



For CDB data sizes less than 32 bytes, the <a href="..\minitape\ns-minitape-_srbex_data_scsi_cdb32.md">SRBEX_DATA_SCSI_CDB32</a> structure, and possibly the <a href="..\minitape\ns-minitape-_srbex_data_scsi_cdb16.md">SRBEX_DATA_SCSI_CDB16</a> structure, may be used instead. The maximum CDB data allowed in the <b>Cdb</b> array is SRBEX_DATA_SCSI_CDB_VAR_LENGTH_MAX - SRBEX_DATA_SCSI_CDB_VAR_LENGTH_MIN + 1. The length specified in <b>CdbLength</b> must be less than or equal to this value.




## -see-also

<a href="..\minitape\ns-minitape-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>



<a href="..\minitape\ns-minitape-_srbex_data_scsi_cdb16.md">SRBEX_DATA_SCSI_CDB16</a>



<a href="..\minitape\ns-minitape-_srbex_data_scsi_cdb32.md">SRBEX_DATA_SCSI_CDB32</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SRBEX_DATA_SCSI_CDB_VAR structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

