---
UID: NS:srb._SRBEX_DATA_WMI
title: _SRBEX_DATA_WMI (srb.h)
description: The SRBEX_DATA_WMI structure contains the request data for an extended WMI SRB.
old-location: storage\srbex_data_wmi.htm
tech.root: storage
ms.assetid: 3FFBF258-50C3-4D2D-AFC8-184D2FF85EE4
ms.date: 03/29/2018
keywords: ["_SRBEX_DATA_WMI structure"]
ms.keywords: "*PSRBEX_DATA_WMI, PSRBEX_DATA_WMI, PSRBEX_DATA_WMI structure pointer [Storage Devices], SRBEX_DATA_WMI, SRBEX_DATA_WMI structure [Storage Devices], _SRBEX_DATA_WMI, storage.srbex_data_wmi, storport/PSRBEX_DATA_WMI, storport/SRBEX_DATA_WMI"
f1_keywords:
 - "srb/SRBEX_DATA_WMI"
 - "SRBEX_DATA_WMI"
req.header: srb.h
req.include-header: Storport.h, Srb.h, Minitape.h
req.target-type: Windows
req.target-min-winverclnt: Available  starting with Windows 8.
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
- SRBEX_DATA_WMI
targetos: Windows
req.typenames: SRBEX_DATA_WMI, *PSRBEX_DATA_WMI
---

# _SRBEX_DATA_WMI structure


## -description


The <b>SRBEX_DATA_WMI</b> structure contains the request data for an extended WMI SRB.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Type

Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypeWmi</b>.


### -field Length

Length of the data in this structure starting with the <b>WMISubFunction</b> member. Set to SRBEX_DATA_WMI_LENGTH.


### -field WMISubFunction

Indicates the WMI action to be performed. The subfunction value corresponds to the WMI minor IRP number that identifies the WMI operation. 


### -field WMIFlags

Indicates that the WMI request is for the adapter if SRB_WMI_FLAGS_ADAPTER_REQUEST is set and that storage device address is reserved. Otherwise, <i>WMIFlags</i> will be <b>NULL</b>, indicating that the request is for the storage device specified by an address at <b>AddressOffset</b> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a> structure.


### -field Reserved

This member is reserved. Contains zeros.


### -field Reserved1

This member is reserved. Set to 0.


### -field DataPath

Specifies the WMI data path for this request.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>
 

 

