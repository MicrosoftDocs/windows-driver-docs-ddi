---
UID: NS:ucmucsippmrequests._UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS
title: _UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS (ucmucsippmrequests.h)
tech.root: usbref
description: Contains a USCI data block for input to IOCTL_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK.
ms.assetid: b52e3688-b7d0-4a31-9769-706ea2ac0e17
ms.date: 09/30/2018
keywords: ["_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS structure"]
f1_keywords:
 - "ucmucsippmrequests/_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS"
 - "_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS"
ms.keywords: _UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS, UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS, *PUCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS, 
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
req.typenames: UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS, *PUCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ucmucsippmrequests.h
api_name: 
- _UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS structure

## -description
Contains a USCI data block. This structure is the input buffer to the [IOCTL_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK](ni-ucmucsippmrequests-ioctl_ucmucsi_ppm_send_ucsi_data_block.md) I/O request.

## -struct-fields

### -field PpmObject
A handle to a Platform Policy Manager (PPM) object that the client driver received in the previous call to [**UcmUcsiPpmCreate**](../ucmucsippm/nf-ucmucsippm-ucmucsippmcreate.md).
 
### -field UcmUcsiDataBlock
A [**UCSI_DATA_BLOCK**](../ucmucsispec/ns-ucmucsispec-_ucsi_data_block.md) structure that contains the data block to send.  

## -remarks

## -see-also
[IOCTL_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK](ni-ucmucsippmrequests-ioctl_ucmucsi_ppm_send_ucsi_data_block.md)
