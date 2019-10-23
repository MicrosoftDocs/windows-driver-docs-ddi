---
UID: NF:srb.ScsiPortFreeDeviceBase
title: ScsiPortFreeDeviceBase function (srb.h)
description: The ScsiPortFreeDeviceBase routine frees a range of device I/O or memory space addresses previously mapped into the system address space with ScsiPortGetDeviceBase.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\scsiportfreedevicebase.htm
tech.root: storage
ms.assetid: 391f3b20-175f-4b27-b30f-34ccc43ca650
ms.date: 03/29/2018
ms.keywords: ScsiPortFreeDeviceBase, ScsiPortFreeDeviceBase routine [Storage Devices], scsiprt_e74eafd2-bedf-46d2-b71a-fb36b6bba128.xml, srb/ScsiPortFreeDeviceBase, storage.scsiportfreedevicebase
ms.topic: function
f1_keywords:
 - "srb/ScsiPortFreeDeviceBase"
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
req.target-type: Desktop
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
req.lib: Scsiport.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Scsiport.lib
- Scsiport.dll
api_name:
- ScsiPortFreeDeviceBase
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortFreeDeviceBase function


## -description


The <b>ScsiPortFreeDeviceBase</b> routine frees a range of device I/O or memory space addresses previously mapped into the system address space with <b>ScsiPortGetDeviceBase</b>.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param HwDeviceExtension [in]

Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension->HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportinitialize">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param MappedAddress [in]

Pointer to the base address of the range to be freed. This address must be the same as that returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>.


## -returns



None




## -remarks



If a miniport driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)">HwScsiFindAdapter</a> routine determines that the driver does not need a particular mapped base address for an adapter, it must release the mapping by calling this routine. For example, when a miniport driver determines there are no supported HBAs on a particular I/O bus, it must call <b>ScsiPortFreeDeviceBase</b> with each mapped address returned by <b>ScsiPortGetDeviceBase</b>, if any calls to this routine were made.

<b>ScsiPortFreeDeviceBase</b> can be called only from miniport driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)">HwScsiFindAdapter</a> routine. Calls from other miniport driver routines will result in system failure or incorrect operation for the caller.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)">HwScsiFindAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
 

 

