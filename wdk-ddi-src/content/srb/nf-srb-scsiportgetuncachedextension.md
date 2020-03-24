---
UID: NF:srb.ScsiPortGetUncachedExtension
title: ScsiPortGetUncachedExtension function (srb.h)
description: The ScsiPortGetUncachedExtension routine allocates memory that can be used by both the CPU and a bus-master HBA for DMA or for shared data.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportgetuncachedextension.htm
tech.root: storage
ms.assetid: d32da7d9-7f26-4c99-8c10-3b9e1a7c9c22
ms.date: 03/29/2018
keywords: ["ScsiPortGetUncachedExtension function"]
ms.keywords: ScsiPortGetUncachedExtension, ScsiPortGetUncachedExtension routine [Storage Devices], scsiprt_b3764d3f-3e99-4a2f-b17c-30d6fcafe255.xml, srb/ScsiPortGetUncachedExtension, storage.scsiportgetuncachedextension
f1_keywords:
 - "srb/ScsiPortGetUncachedExtension"
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
- ScsiPortGetUncachedExtension
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortGetUncachedExtension function


## -description


The <b>ScsiPortGetUncachedExtension</b> routine allocates memory that can be used by both the CPU and a bus-master HBA for DMA or for shared data.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param HwDeviceExtension [in]

Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension->HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportinitialize">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param ConfigInfo [in]

Specifies information about the HBA's DMA capabilities. The following members must be filled in: <b>DmaChannel</b> or <b>DmaPort</b>, <b>DmaWidth</b>, <b>DmaSpeed</b>, <b>MaximumTransferLength</b>, <b>ScatterGather</b>, <b>Master</b> set to <b>TRUE</b>, <b>NumberOfPhysicalBreaks</b>, <b>AdapterInterfaceType</b>, <b>Dma32BitAddresses</b>, <b>SystemIoBusNumber</b>, <b>AutoRequestSense</b>, and <b>SrbExtensionSize.</b>

Members that are not pertinent to the HBA, such as <b>DmaChannel</b> for an EISA bus-master adapter, must be left as is.


### -param NumberOfBytes [in]

Indicates the size in bytes of the uncached extension to be allocated. Drivers in Windows XP and earlier operating systems must not allocate more than 100 kilobytes of uncached extension, and if they participate in I/O operations on the hibernation file or the crash dump file, they must limit the amount of uncached extension that they allocate to under 32 kilobytes. 


## -returns



<b>ScsiPortGetUncachedExtension</b> returns a virtual address pointer to the uncached extension. If it cannot allocate the requested memory, it returns <b>NULL</b>.




## -remarks



<b>ScsiPortGetUncachedExtension</b> can be called only from miniport driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)">HwScsiFindAdapter</a> routine and only for a bus-master HBA. Calls from other miniport driver routines will result in system failure or incorrect operation for the caller.

Because high-end machines have caches and large memories, any memory to be shared between an HBA and the CPU must be specially allocated. Mailboxes or I/O request queues in system memory are examples of this type of shared memory.

A miniport driver must set <b>SrbExtensionSize.</b> before calling <b>ScsiPortGetUncachedExtension</b> to change the size of its per-request storage based on <b>NumberOfPhysicalBreaks</b>.

The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)">HwScsiFindAdapter</a> routine can call <b>ScsiPortGetUncachedExtension</b> only once for each bus-master HBA the miniport driver supports.

To obtain the physical address for the uncached extension that the HBA can use, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetphysicaladdress">ScsiPortGetPhysicalAddress</a>.

The ScsiPort driver will free the memory allocated by <b>ScsiPortGetUncachedExtension</b> when the adapter device is stopped.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)">HwScsiFindAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_port_configuration_information">PORT_CONFIGURATION_INFORMATION (SCSI)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetphysicaladdress">ScsiPortGetPhysicalAddress</a>
 

 

