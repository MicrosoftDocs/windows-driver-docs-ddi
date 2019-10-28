---
UID: NS:srb._SRBEX_DATA_SCSI_CDB32
title: _SRBEX_DATA_SCSI_CDB32 (srb.h)
description: The SRBEX_DATA_SCSI_CDB32 structure contains the extended SRB data for a 32-byte SCSI command data block (CDB).
old-location: storage\srbex_data_scsi_cdb32.htm
tech.root: storage
ms.assetid: 8BE53883-2FD0-4CAB-928E-532587DA80C3
ms.date: 03/29/2018
ms.keywords: "*PSRBEX_DATA_SCSI_CDB32, PSRBEX_DATA_SCSI_CDB32, PSRBEX_DATA_SCSI_CDB32 structure pointer [Storage Devices], SRBEX_DATA_SCSI_CDB32, SRBEX_DATA_SCSI_CDB32 structure [Storage Devices], _SRBEX_DATA_SCSI_CDB32, storage.srbex_data_scsi_cdb32, storport/PSRBEX_DATA_SCSI_CDB32, storport/SRBEX_DATA_SCSI_CDB32"
ms.topic: struct
f1_keywords:
 - "srb/SRBEX_DATA_SCSI_CDB32"
req.header: srb.h
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
- SRBEX_DATA_SCSI_CDB32
product:
- Windows
targetos: Windows
req.typenames: SRBEX_DATA_SCSI_CDB32, *PSRBEX_DATA_SCSI_CDB32
---

# _SRBEX_DATA_SCSI_CDB32 structure


## -description


The <b>SRBEX_DATA_SCSI_CDB32</b> structure contains the extended SRB data for a 32-byte SCSI command data block (CDB).
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_srbex_data_scsi_cdb16">SRBEX_DATA_SCSI_CDB16</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>
 

 

