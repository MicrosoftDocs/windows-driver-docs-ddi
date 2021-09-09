---
UID: NF:storport.StorPortGetPfns
title: StorPortGetPfns function (storport.h)
description: The StorPortGetPfns routine can be called when a miniport needs to retreive PFNs associated with a MDL for a SRB.
old-location: storage\storportgetpfns.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortGetPfns function"]
ms.keywords: StorPortGetPfns, StorPortGetPfns routine [Storage Devices], storage.storportgetpfns, storport/StorPortGetPfns
req.header: storport.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortGetPfns
 - storport/StorPortGetPfns
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Storport.h
api_name:
 - StorPortGetPfns
---

# StorPortGetPfns function

## -description

The **StorPortGetPfns** routine can be called when a miniport needs to retreive PFNs associated with a MDL for a SRB.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver.

### -param Srb

[in] A pointer to the source SCSI request block (SRB).

### -param Mdl

[in] A pointer to the MDL for which Pfns are requested. Only MDLs obtained using **StorPortGetOriginalMdl** or **StorPortGetDataInBufferMdl** are supported.

### -param Pfns

[out] A pointer to the beginning of the array of physical page numbers that are associated with the MDL. Callers must NOT modify or update or free the list.

### -param PfnCount

[out] Specifies the number of PFNs in the array.

### -param StartingOffset

[out] Specifies the byte offset within the initial page of the buffer described by the given MDL.

## -returns

**StorPortGetPfns** returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_NOT_IMPLEMENTED   | This function is not implemented on the active operating system. |
| STOR_STATUS_SUCCESS           | The list items were removed successfully or the list is already empty. |
| STOR_STATUS_INVALID_PARAMETER | A pointer to one of the parameters is **NULL**. |

## -remarks

 Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver in the **DeviceExtension->HwDeviceExtension** member of the device object for the HBA immediately after the miniport driver calls [**StorPortInitialize**](nf-storport-storportinitialize.md). The port driver frees this memory when it removes the device.

Starting in Windows 8, the **Srb** parameter may point to either [**SCSI_REQUEST_BLOCK**](../srb/ns-srb-_scsi_request_block.md) or [**STORAGE_REQUEST_BLOCK**](../srb/ns-srb-_storage_request_block.md).

## -see-also

[**StorPortGetDataInBufferMdl**](nf-storport-storportgetdatainbuffermdl.md)

[**StorPortGetOriginalMdl**](nf-storport-storportgetoriginalmdl.md)

[**StorPortInitialize**](nf-storport-storportinitialize.md)
