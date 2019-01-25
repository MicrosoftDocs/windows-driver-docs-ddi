---
UID: NS:ucmucsippmrequests._UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_IN_PARAMS
title: _UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_IN_PARAMS (ucmucsippmrequests.h)
tech.root: usbref
description: Contains a USCI data block for input to IOCTL_UCMUCSI_PPM_GET_UCSI_DATA_BLOCK.
ms.assetid: 3ff1274f-918e-4181-b20b-4674b8048c44
ms.date: 09/30/2018
ms.topic: struct
ms.keywords: _UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_IN_PARAMS, UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_IN_PARAMS, *PUCMUCSI_PPM_GET_UCSI_DATA_BLOCK_IN_PARAMS, 
req.header: ucmucsippmrequests.h
req.include-header: UcmUcsiCx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_IN_PARAMS, *PUCMUCSI_PPM_GET_UCSI_DATA_BLOCK_IN_PARAMS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ucmucsippmrequests.h
api_name: 
-	_UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_IN_PARAMS
product: Windows
targetos: Windows
ms.custom: RS5
---

# _UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_IN_PARAMS structure

## -description
Contains a USCI data block. This structure is the input buffer to the [IOCTL_UCMUCSI_PPM_GET_UCSI_DATA_BLOCK](ni-ucmucsippmrequests-ioctl_ucmucsi_ppm_get_ucsi_data_block.md) I/O request.

## -struct-fields

### -field PpmObject
A handle to a Platform Policy Manager (PPM) object that the client driver received in the previous call to [**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md). 

## -remarks

## -see-also
[IOCTL_UCMUCSI_PPM_GET_UCSI_DATA_BLOCK](ni-ucmucsippmrequests-ioctl_ucmucsi_ppm_get_ucsi_data_block.md)
