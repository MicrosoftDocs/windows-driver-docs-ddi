---
UID: NS:irb._IDE_TRANSFER_MODE_PARAMETERS
title: "_IDE_TRANSFER_MODE_PARAMETERS"
author: windows-driver-content
description: The IDE_TRANSFER_MODE_PARAMETERS structure is used in conjunction with the miniport driver's AtaControllerTransferModeSelect routine to set the transfer mode parameters on a channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\ide_transfer_mode_parameters.htm
old-project: storage
ms.assetid: 66e6efd0-6651-4c87-94ba-d9d3b9191339
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: structs-ATA_41b44f2c-8685-45fe-8c56-2a9a648782b4.xml, storage.ide_transfer_mode_parameters, IDE_TRANSFER_MODE_PARAMETERS structure [Storage Devices], PIDE_TRANSFER_MODE_PARAMETERS, PIDE_TRANSFER_MODE_PARAMETERS structure pointer [Storage Devices], _IDE_TRANSFER_MODE_PARAMETERS, IDE_TRANSFER_MODE_PARAMETERS, irb/PIDE_TRANSFER_MODE_PARAMETERS, *PIDE_TRANSFER_MODE_PARAMETERS, irb/IDE_TRANSFER_MODE_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: irb.h
req.include-header: Irb.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	irb.h
apiname:
-	IDE_TRANSFER_MODE_PARAMETERS
product: Windows
targetos: Windows
req.typenames: IDE_TRANSFER_MODE_PARAMETERS, *PIDE_TRANSFER_MODE_PARAMETERS
---

# _IDE_TRANSFER_MODE_PARAMETERS structure


## -description


The IDE_TRANSFER_MODE_PARAMETERS structure is used in conjunction with the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550143">AtaControllerTransferModeSelect</a> routine to set the transfer mode parameters on a channel.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _IDE_TRANSFER_MODE_PARAMETERS {
  UCHAR           ChannelNumber;
  IDE_DEVICE_TYPE DeviceType[MAX_IDE_DEVICE];
  BOOLEAN         IoReadySupported[MAX_IDE_DEVICE];
  ULONG           DeviceTransferModeSupported[MAX_IDE_DEVICE];
  ULONG           DeviceTransferModeCurrent[MAX_IDE_DEVICE];
  ULONG           DeviceTransferModeSelected[MAX_IDE_DEVICE];
} IDE_TRANSFER_MODE_PARAMETERS, *PIDE_TRANSFER_MODE_PARAMETERS;
````


## -struct-fields




### -field ChannelNumber

Indicates the channel number whose mode parameters are to be set.


### -field DeviceType

Contains an enumeration value of type <a href="..\irb\ne-irb-ide_device_type.md">IDE_DEVICE_TYPE</a> that indicates the type of device. The miniport driver should not select a transfer mode if the device type is <b>DeviceNotExist</b>.


### -field IoReadySupported

Indicates when <b>TRUE</b> that bit 11 of word 49 of the indicated device's identify data is set to 1. An IDE request with a function value of IRB_FUNCTION_ATA_IDENTIFY will retrieve a device's identify data. For more information about ATA identify data, see the sections on the Identify Device information packet in version 6.0 of the <i>ATA/ATAPI specification</i>.


### -field DeviceTransferModeSupported

Contains a bitmap that indicates the supported transfer modes for each of the devices on the channel. The port driver sets this member. The miniport driver must not select a transfer mode that the port driver does not support. For more information about this member, see the <b>Remarks</b> section.


### -field DeviceTransferModeCurrent

Contains a bitmap that indicates the current transfer mode settings for each of the device on the channel. The port driver retrieves the current transfer mode of the devices from their identify device data. For more information about this member, see the <b>Remarks</b> section.


### -field DeviceTransferModeSelected

Contains a bitmap that indicates the selected transfer mode settings for each of the device on the channel. The miniport driver should use this member to indicate to the port driver which transfer modes it selects. For more information about this member, see the <b>Remarks</b> section.


## -remarks



Member arrays <b>DeviceTransferModeSupported</b>, <b>DeviceTransferModeCurrent</b>, and <b>DeviceTransferModeSelected</b> are arrays of ULONG bitmaps indicating combinations of PIO and DMA transfer modes. The bitmaps are defined as follows:

// PIO Modes

#define PIO_MODE0           (1 &lt;&lt; 0)

#define PIO_MODE1           (1 &lt;&lt; 1)

#define PIO_MODE2           (1 &lt;&lt; 2)

#define PIO_MODE3           (1 &lt;&lt; 3)

#define PIO_MODE4           (1 &lt;&lt; 4)

// Single-word DMA Modes

#define SWDMA_MODE0         (1 &lt;&lt; 5)

#define SWDMA_MODE1         (1 &lt;&lt; 6)

#define SWDMA_MODE2         (1 &lt;&lt; 7)

// Multi-word DMA Modes

#define MWDMA_MODE0         (1 &lt;&lt; 8)

#define MWDMA_MODE1         (1 &lt;&lt; 9)

#define MWDMA_MODE2         (1 &lt;&lt; 10)

// Ultra DMA Modes

#define UDMA_MODE0          (1 &lt;&lt; 11)

#define UDMA_MODE1          (1 &lt;&lt; 12)

#define UDMA_MODE2          (1 &lt;&lt; 13)

#define UDMA_MODE3          (1 &lt;&lt; 14)

#define UDMA_MODE4          (1 &lt;&lt; 15)

#define UDMA_MODE5          (1 &lt;&lt; 16)




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550143">AtaControllerTransferModeSelect</a>



<a href="..\irb\ne-irb-ide_device_type.md">IDE_DEVICE_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IDE_TRANSFER_MODE_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

