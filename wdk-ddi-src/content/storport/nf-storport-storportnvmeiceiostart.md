---
UID: NF:storport.StorPortNvmeIceIoStart
tech.root: storage
title: StorPortNvmeIceIoStart
ms.date: 07/26/2024
targetos: Windows
description: Learn more about the StorPortNvmeIceIoStart function.
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
 - StorPortNvmeIceIoStart
f1_keywords:
 - StorPortNvmeIceIoStart
 - storport/StorPortNvmeIceIoStart
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortNvmeIceIoStart
---

## -description

The **StorPortNvmeIceIoStart** function initiates an NVMe ICE (instant cryptographic erase) I/O operation.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the hardware device extension. This is a per HBA (Host Bus Adapter) context area provided by the miniport driver. The miniport driver can store HBA-specific information here.

### -param Srb

[in] A pointer to a SCSI request block. This structure represents a single I/O request.

### -param LbaCount

[in] The number of logical block addresses (LBAs) to be transferred.

### -param PrpCount

[in] The number of physical region pages (PRPs) to be transferred.

### -param Prp1

[in/out] A pointer to the first PRP, used in NVMe to describe the physical memory locations involved in the data transfer.

### -param Prp2

[in/out] A pointer to the second PRP, used in NVMe to describe the physical memory locations involved in the data transfer.

### -param PrpList

[in/out] A pointer to a list of additional PRPs.

## -returns

**StorPortNvmeIceIoStart** returns STOR_STATUS_SUCCESS if the operation is successful. Otherwise, it returns a STOR_STATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_NOT_IMPLEMENTED | This function isn't implemented on the active operating system. |
| STOR_STATUS_INVALID_PARAMETER | One of the parameters is invalid. |

## -remarks

## -see-also

[**StorPortNvmeIceIoComplete**](nf-storport-storportnvmeiceiocomplete.md)
