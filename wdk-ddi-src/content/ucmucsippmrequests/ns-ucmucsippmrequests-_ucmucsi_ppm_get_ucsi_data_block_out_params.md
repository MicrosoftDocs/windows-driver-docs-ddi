---
UID: NS:ucmucsippmrequests._UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_OUT_PARAMS
title: _UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_OUT_PARAMS (ucmucsippmrequests.h)
tech.root: usbref
description: Contains a USCI data block for output to IOCTL_UCMUCSI_PPM_GET_UCSI_DATA_BLOCK.
ms.assetid: c2710a84-7eaa-44bf-a0b3-4ea40f0b03a3
ms.date: 09/30/2018
ms.topic: struct
ms.keywords: _UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_OUT_PARAMS, UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_OUT_PARAMS, *PUCMUCSI_PPM_GET_UCSI_DATA_BLOCK_OUT_PARAMS, 
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
req.typenames: UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_OUT_PARAMS, *PUCMUCSI_PPM_GET_UCSI_DATA_BLOCK_OUT_PARAMS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ucmucsippmrequests.h
api_name: 
-	_UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_OUT_PARAMS
product: Windows
targetos: Windows
ms.custom: RS5
---

# _UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_OUT_PARAMS structure

## -description
Contains a USCI data block. This structure is the output buffer to the [IOCTL_UCMUCSI_PPM_GET_UCSI_DATA_BLOCK](ni-ucmucsippmrequests-ioctl_ucmucsi_ppm_get_ucsi_data_block.md) I/O request.

## -struct-fields

### -field UcmUcsiDataBlock
A [**UCSI_DATA_BLOCK**](../ucmucsispec/ns-ucmucsispec-_ucsi_data_block.md) structure that receives the data block with notification information. 

## -remarks

## -see-also
[IOCTL_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK](ni-ucmucsippmrequests-ioctl_ucmucsi_ppm_send_ucsi_data_block.md)
