---
UID: NS:irb._IDE_CONTROLLER_CONFIGURATION
title: "_IDE_CONTROLLER_CONFIGURATION"
author: windows-driver-content
description: The IDE_CONTROLLER_CONFIGURATION structure is used to pass controller configuration information between the port driver and the miniport driver.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_controller_configuration.htm
old-project: storage
ms.assetid: 89b7f66e-3a3a-4723-a409-3b3030c1a45b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PIDE_CONTROLLER_CONFIGURATION, storage.ide_controller_configuration, PIDE_CONTROLLER_CONFIGURATION structure pointer [Storage Devices], irb/IDE_CONTROLLER_CONFIGURATION, *PIDE_CONTROLLER_CONFIGURATION, structs-ATA_c72d9d21-e06b-43e0-8854-8b682e2e0778.xml, IDE_CONTROLLER_CONFIGURATION, IDE_CONTROLLER_CONFIGURATION structure [Storage Devices], irb/PIDE_CONTROLLER_CONFIGURATION, _IDE_CONTROLLER_CONFIGURATION
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
-	IDE_CONTROLLER_CONFIGURATION
product: Windows
targetos: Windows
req.typenames: IDE_CONTROLLER_CONFIGURATION, *PIDE_CONTROLLER_CONFIGURATION
---

# _IDE_CONTROLLER_CONFIGURATION structure


## -description


The IDE_CONTROLLER_CONFIGURATION structure is used to pass controller configuration information between the port driver and the miniport driver.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _IDE_CONTROLLER_CONFIGURATION {
  USHORT                  Version;
  UCHAR                   NumberOfChannels;
  IDE_OPERATION_MODE      ControllerMode;
  UCHAR                   NumberOfPhysicalBreaks;
  ULONG                   MaximumTransferLength;
  BOOLEAN                 Reserved;
  BOOLEAN                 NativeModeEnabled;
  BOOLEAN                 Dma64BitAddress;
  BOOLEAN                 BusMaster;
  IDE_BUS_TYPE            AtaBusType;
  PIDE_MINIPORT_RESOURCES ControllerResources;
} IDE_CONTROLLER_CONFIGURATION, *PIDE_CONTROLLER_CONFIGURATION;
````


## -struct-fields




### -field Version

The port driver sets this field to indicate the version of the port driver. The port driver sets the version to sizeof(IDE_CONTROLLER_CONFIGURATION). The miniport driver should verify that the version is greater than or equal to the one it is using.


### -field NumberOfChannels

Specifies the number of channels supported by the HBA. Note that this indicates the total number of channels including the ones that are disabled.


### -field ControllerMode

The port driver sets this field to inform the ATA miniport which mode it is running at. There are two possible modes:
  

<table>
<tr>
<th>Mode</th>
<th>Description</th>
</tr>
<tr>
<td>
IdeModeNormal 

</td>
<td>
This is the standard full capabilities mode where the ATA miniport may operate normally.

</td>
</tr>
<tr>
<td>
IdeModeDump

</td>
<td>
This is the limited no memory mode that an ATA miniport operates in during hibernate or crashdump. Call Back Routines and Registry Access Routines cannot be used when in this mode.

</td>
</tr>
</table>
 


### -field NumberOfPhysicalBreaks

Specifies the maximum number of breaks between address ranges that a data buffer can have if the HBA supports scatter/gather. In other words, the number of scatter/gather lists minus one. By default, the value of this member is IDE_UNINITIALIZED_VALUE, which indicates the HBA can support an unlimited number of physical discontiguities. If the port driver sets a value for this member, the miniport driver can adjust the value lower but no higher. If this member is IDE_UNINITIALIZED_VALUE, the miniport driver must reset this member according to the HBA's scatter/gather capacity.


### -field MaximumTransferLength

Specifies the maximum number of bytes the HBA can transfer in a single transfer operation. By default, the value of this member is IDE_UNINITIALIZED_VALUE, which indicates an unlimited maximum transfer size.


### -field Reserved

Reserved for future use. The miniport driver must not use this field.


### -field NativeModeEnabled

The miniport driver could set this member to <b>TRUE</b> to indicate that the controller is to be operated in Native mode.


### -field Dma64BitAddress

The miniport driver could set this member to <b>TRUE</b> to indicate support for 64 bit DMA operation.


### -field BusMaster

The miniport driver could set this member to <b>TRUE</b> to indicate bus mastering support.


### -field AtaBusType

Indicates whether it is a SATA or a PATA controller.


### -field ControllerResources

Provides the hardware resources for the ATA controller.

