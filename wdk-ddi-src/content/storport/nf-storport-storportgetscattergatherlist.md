---
UID: NF:storport.StorPortGetScatterGatherList
title: StorPortGetScatterGatherList function (storport.h)
description: The StorPortGetScatterGatherList routine retrieves the associated scatter/gather list for the specified SCSI request block (SRB).
old-location: storage\storportgetscattergatherlist.htm
tech.root: storage
ms.assetid: ddb7052d-b9f3-40f6-b00a-6bf52f010cdc
ms.date: 03/29/2018
keywords: ["StorPortGetScatterGatherList function"]
ms.keywords: StorPortGetScatterGatherList, StorPortGetScatterGatherList routine [Storage Devices], storage.storportgetscattergatherlist, storport/StorPortGetScatterGatherList, storprt_1736d395-ccc8-42ec-8d84-a9d3b7656996.xml
req.header: storport.h
req.include-header: Storport.h
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
req.lib: Storport.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortGetScatterGatherList
 - storport/StorPortGetScatterGatherList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortGetScatterGatherList
---

# StorPortGetScatterGatherList function


## -description

The <b>StorPortGetScatterGatherList</b> routine retrieves the associated scatter/gather list for the specified SCSI request block (SRB).

## -parameters

### -param HwDeviceExtension 

[in]
A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport immediately after the miniport driver calls <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device.

### -param Srb 

[in]
Pointer to the SRB for which the scatter gather list is to be constructed.

## -returns

<b>StorPortGetScatterGatherList</b> returns a pointer to the scatter/gather list.

## -remarks

This routine is provided with the Storport driver library. There is no parallel routine provided in the SCSI port library. 

The pointer to the scatter/gather list that is returned is valid only until the SRB is completed. 

The miniport driver does not have to free the memory for the scatter/gather list that <b>StorPortGetScatterGatherList</b> returns. 

The miniport driver must not modify the scatter/gather list.

Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a> or <a href="/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>



<a href="/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>



<a href="/windows-hardware/drivers/ddi/storport/ns-storport-_stor_scatter_gather_element">STOR_SCATTER_GATHER_ELEMENT</a>



<a href="/windows-hardware/drivers/ddi/storport/ns-storport-_stor_scatter_gather_list">STOR_SCATTER_GATHER_LIST</a>