---
UID: NS:minitape._SRBEX_DATA_SCSI_CDB_VAR
title: _SRBEX_DATA_SCSI_CDB_VAR (minitape.h)
description: The SRBEX_DATA_SCSI_CDB_VAR structure contains the extended SRB data for a variable length SCSI command data block (CDB).
old-location: storage\srbex_data_scsi_cdb_var.htm
tech.root: storage
ms.assetid: 8D3BD2E0-02EA-4745-AA1C-86D829E6BA81
ms.date: 03/29/2018
ms.keywords: "*PSRBEX_DATA_SCSI_CDB_VAR, PSRBEX_DATA_SCSI_CDB_VAR, PSRBEX_DATA_SCSI_CDB_VAR structure pointer [Storage Devices], SRBEX_DATA_SCSI_CDB_VAR, SRBEX_DATA_SCSI_CDB_VAR structure [Storage Devices], _SRBEX_DATA_SCSI_CDB_VAR, storage.srbex_data_scsi_cdb_var, storport/PSRBEX_DATA_SCSI_CDB_VAR, storport/SRBEX_DATA_SCSI_CDB_VAR"
ms.topic: struct
req.header: minitape.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Storport.h
api_name:
- SRBEX_DATA_SCSI_CDB_VAR
product:
- Windows
targetos: Windows
req.typenames: SRBEX_DATA_SCSI_CDB_VAR, *PSRBEX_DATA_SCSI_CDB_VAR
---

# _SRBEX_DATA_SCSI_CDB_VAR structure


## -description


The <b>SRBEX_DATA_SCSI_CDB_VAR</b> structure contains the extended SRB data for a variable length SCSI command data block (CDB).
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

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



For CDB data sizes less than 32 bytes, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_scsi_cdb32">SRBEX_DATA_SCSI_CDB32</a> structure, and possibly the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_scsi_cdb16">SRBEX_DATA_SCSI_CDB16</a> structure, may be used instead. The maximum CDB data allowed in the <b>Cdb</b> array is SRBEX_DATA_SCSI_CDB_VAR_LENGTH_MAX - SRBEX_DATA_SCSI_CDB_VAR_LENGTH_MIN + 1. The length specified in <b>CdbLength</b> must be less than or equal to this value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_scsi_cdb16">SRBEX_DATA_SCSI_CDB16</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_scsi_cdb32">SRBEX_DATA_SCSI_CDB32</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>
 

 

