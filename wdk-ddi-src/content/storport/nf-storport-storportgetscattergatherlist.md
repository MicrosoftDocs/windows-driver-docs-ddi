---
UID: NF:storport.StorPortGetScatterGatherList
title: StorPortGetScatterGatherList function
author: windows-driver-content
description: The StorPortGetScatterGatherList routine retrieves the associated scatter/gather list for the specified SCSI request block (SRB).
old-location: storage\storportgetscattergatherlist.htm
old-project: storage
ms.assetid: ddb7052d-b9f3-40f6-b00a-6bf52f010cdc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , G, L, P, S, StorPortGetScatterGatherList, StorPortGetScatterGatherList routine [Storage Devices], a, c, e, h, i, o, r, s, storage.storportgetscattergatherlist, storport/StorPortGetScatterGatherList, storprt_1736d395-ccc8-42ec-8d84-a9d3b7656996.xml, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortGetScatterGatherList
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortGetScatterGatherList function


## -description


The <b>StorPortGetScatterGatherList</b> routine retrieves the associated scatter/gather list for the specified SCSI request block (SRB). 


## -syntax


````
STORPORT_API PSTOR_SCATTER_GATHER_LIST StorPortGetScatterGatherList(
  _In_ PVOID               HwDeviceExtension,
  _In_ PSCSI_REQUEST_BLOCK Srb
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param Srb [in]

Pointer to the SRB for which the scatter gather list is to be constructed. 


## -returns



<b>StorPortGetScatterGatherList</b> returns a pointer to the scatter/gather list. 




## -remarks



This routine is provided with the Storport driver library. There is no parallel routine provided in the SCSI port library. 

The pointer to the scatter/gather list that is returned is valid only until the SRB is completed. 

The miniport driver does not have to free the memory for the scatter/gather list that <b>StorPortGetScatterGatherList</b> returns. 

The miniport driver must not modify the scatter/gather list.

Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="..\storport\ns-storport-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a> or <a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.




## -see-also

<a href="..\storport\ns-storport-_stor_scatter_gather_list.md">STOR_SCATTER_GATHER_LIST</a>



<a href="..\storport\ns-storport-_stor_scatter_gather_element.md">STOR_SCATTER_GATHER_ELEMENT</a>



<a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>



<a href="..\storport\ns-storport-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetScatterGatherList routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

