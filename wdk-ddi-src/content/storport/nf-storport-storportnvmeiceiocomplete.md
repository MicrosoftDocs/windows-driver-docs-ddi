---
UID: NF:storport.StorPortNvmeIceIoComplete
tech.root: storage
title: StorPortNvmeIceIoComplete
ms.date: 07/26/2024
targetos: Windows
description: Learn more about the StorPortNvmeIceIoComplete function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortNvmeIceIoComplete
f1_keywords:
 - StorPortNvmeIceIoComplete
 - storport/StorPortNvmeIceIoComplete
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortNvmeIceIoComplete
---

## -description

The **StorPortNvmeIceIoComplete** function signals the completion of an NVMe I/O operation that was initiated by a previous call to [**StorPortNvmeIceIoStart**](nf-storport-storportnvmeiceiostart.md).

## -parameters

### -param HwDeviceExtension

[in] A pointer to the hardware device extension for the host bus adapter (HBA).

### -param Srb

[in] A pointer to a SCSI request block. This structure represents a single I/O request.

## -returns

**StorPortNvmeIceIoComplete** returns STOR_STATUS_SUCCESS if the operation is successful. Otherwise, it returns a STOR_STATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_NOT_IMPLEMENTED | This function isn't implemented on the active operating system. |
| STOR_STATUS_INVALID_PARAMETER | One of the parameters is invalid. |

## -remarks

## -see-also

[**StorPortNvmeIceIoStart**](nf-storport-storportnvmeiceiostart.md)
