---
UID: NF:storport.StorPortCompleteRequest
title: StorPortCompleteRequest function (storport.h)
description: The StorPortCompleteRequest routine completes all outstanding requests setting the SRB status value to SrbStatus.
old-location: storage\storportcompleterequest.htm
tech.root: storage
ms.assetid: 20ee0633-a743-46e8-a094-37099b8e4427
ms.date: 03/29/2018
keywords: ["StorPortCompleteRequest function"]
ms.keywords: StorPortCompleteRequest, StorPortCompleteRequest routine [Storage Devices], storage.storportcompleterequest, storport/StorPortCompleteRequest, storprt_c91d5dfe-31de-4804-a0be-c2bab228fbb9.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortCompleteRequest
 - storport/StorPortCompleteRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortCompleteRequest
---

# StorPortCompleteRequest function


## -description

The <b>StorPortCompleteRequest</b> routine completes all outstanding requests setting the SRB status value to <b>SrbStatus</b>.

## -parameters

### -param HwDeviceExtension 

[in]
A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device.

### -param PathId 

[in]
Identifies the SCSI bus. A value of SP_UNTAGGED indicates all buses controlled by the HBA.

### -param TargetId 

[in]
Identifies the target controller or device on the given buses. A value of SP_UNTAGGED indicates all targets on the bus.

### -param Lun 

[in]
Identifies the logical unit for the given target controller or device. A value of SP_UNTAGGED indicates all logical units for the given target controllers on the given buses. Full-duplex miniport drivers must not assign a value of SP_UNTAGGED to this member.

### -param SrbStatus 

[in]
Specifies the completion status to be set in the <b>SrbStatus</b>member of each SRB.

## -returns

None

## -remarks

We do not recommend that writers of Storport miniport drivers use this particular Storport interface routine. Instead, the miniport driver should call StorPortNotification( RequestComplete ) for each outstanding request.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportcompleterequest">ScsiPortCompleteRequest</a>

