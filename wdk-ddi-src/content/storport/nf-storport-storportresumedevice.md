---
UID: NF:storport.StorPortResumeDevice
title: StorPortResumeDevice function (storport.h)
description: The StorPortResumeDevice routine resumes a previously paused logical unit.
old-location: storage\storportresumedevice.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortResumeDevice function"]
ms.keywords: StorPortResumeDevice, StorPortResumeDevice routine [Storage Devices], storage.storportresumedevice, storport/StorPortResumeDevice, storprt_62696d8f-cfb1-43fd-8b23-b14f1ac0d429.xml
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
 - StorPortResumeDevice
 - storport/StorPortResumeDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortResumeDevice
---

# StorPortResumeDevice function


## -description

The <b>StorPortResumeDevice</b> routine resumes a previously paused logical unit.

## -parameters

### -param HwDeviceExtension [in]


A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device.

### -param PathId [in]


Identifies the SCSI bus.

### -param TargetId [in]


Identifies the target controller or device on the bus.

### -param Lun [in]


Identifies the logical unit number of the target device.

## -returns

<b>StorPortResumeDevice</b> returns <b>TRUE</b> if the miniport driver succeeded in resuming the paused device, <b>FALSE</b> if not.

## -see-also

<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportpausedevice">StorPortPauseDevice</a>
