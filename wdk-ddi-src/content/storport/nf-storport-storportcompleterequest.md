---
UID: NF:storport.StorPortCompleteRequest
title: StorPortCompleteRequest function
author: windows-driver-content
description: The StorPortCompleteRequest routine completes all outstanding requests setting the SRB status value to SrbStatus.
old-location: storage\storportcompleterequest.htm
old-project: storage
ms.assetid: 20ee0633-a743-46e8-a094-37099b8e4427
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortCompleteRequest, StorPortCompleteRequest routine [Storage Devices], storage.storportcompleterequest, storport/StorPortCompleteRequest, storprt_c91d5dfe-31de-4804-a0be-c2bab228fbb9.xml
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
req.ddi-compliance: StorPortCompleteRequest, StorPortDDIsPortOnly
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortCompleteRequest
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortCompleteRequest function


## -description


The <b>StorPortCompleteRequest</b> routine completes all outstanding requests setting the SRB status value to <b>SrbStatus</b>. 


## -syntax


````
STORPORT_API VOID StorPortCompleteRequest(
  _In_ PVOID HwDeviceExtension,
  _In_ UCHAR PathId,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun,
  _In_ UCHAR SrbStatus
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param PathId [in]

Identifies the SCSI bus. A value of SP_UNTAGGED indicates all buses controlled by the HBA. 


### -param TargetId [in]

Identifies the target controller or device on the given buses. A value of SP_UNTAGGED indicates all targets on the bus. 


### -param Lun [in]

Identifies the logical unit for the given target controller or device. A value of SP_UNTAGGED indicates all logical units for the given target controllers on the given buses. Full-duplex miniport drivers must not assign a value of SP_UNTAGGED to this member.


### -param SrbStatus [in]

Specifies the completion status to be set in the <b>SrbStatus</b>member of each SRB.


## -returns



None 




## -remarks



We do not recommend that writers of Storport miniport drivers use this particular Storport interface routine. Instead, the miniport driver should call StorPortNotification( RequestComplete ) for each outstanding request.




## -see-also

<a href="..\srb\nf-srb-scsiportcompleterequest.md">ScsiPortCompleteRequest</a>



 

 


