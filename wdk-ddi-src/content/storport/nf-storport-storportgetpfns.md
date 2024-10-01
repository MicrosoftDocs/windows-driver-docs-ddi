---
UID: NF:storport.StorPortGetPfns
title: StorPortGetPfns function (storport.h)
description: Learn more about the StorPortGetPfns function.
tech.root: storage
ms.date: 10/01/2024
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

A miniport can call the **StorPortGetPfns** to retrieve the page frame numbers (Pfns) for the memory described by the specified MDL (memory descriptor list) associated with a SRB.

## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver.

Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver in the **DeviceExtension->HwDeviceExtension** member of the device object for the HBA immediately after the miniport driver calls [**StorPortInitialize**](nf-storport-storportinitialize.md). The port driver frees this memory when it removes the device.

### -param Srb [in]

A pointer to the source SCSI request block (SRB). Starting in Windows 8, the **Srb** parameter can point to either [**SCSI_REQUEST_BLOCK**](../srb/ns-srb-_scsi_request_block.md) or [**STORAGE_REQUEST_BLOCK**](../srb/ns-srb-_storage_request_block.md).

### -param Mdl [in]

A pointer to the MDL for which Pfns are requested. Only MDLs obtained using [**StorPortGetOriginalMdl**](nf-storport-storportgetoriginalmdl.md) or [**StorPortGetDataInBufferMdl**](nf-storport-storportgetdatainbuffermdl.md) are supported.

### -param Pfns [out]

Pointer to an array of Pfns that are associated with the MDL. Callers must not modify, update, or free the list.

### -param PfnCount [out]

The number of Pfns in the array that **Pfns** points to.

### -param StartingOffset [out]

Specifies the byte offset within the initial page of the buffer described by the given MDL.

## -returns

**StorPortGetPfns** returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_NOT_IMPLEMENTED   | This function is not implemented on the active operating system. |
| STOR_STATUS_SUCCESS           | The function completed successfully. |
| STOR_STATUS_INVALID_PARAMETER | A pointer to one of the parameters is **NULL**. |

## -see-also

[**StorPortGetDataInBufferMdl**](nf-storport-storportgetdatainbuffermdl.md)

[**StorPortGetOriginalMdl**](nf-storport-storportgetoriginalmdl.md)

[**StorPortInitialize**](nf-storport-storportinitialize.md)
