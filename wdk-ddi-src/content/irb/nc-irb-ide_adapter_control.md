---
UID: NC:irb.IDE_ADAPTER_CONTROL
title: IDE_ADAPTER_CONTROL (irb.h)
description: The AtaAdapterControl miniport driver routine is called to perform Plug and Play (PnP) and Power Management operations on the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataadaptercontrol.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IDE_ADAPTER_CONTROL callback function"]
ms.keywords: AtaAdapterControl, AtaAdapterControl routine [Storage Devices], IDE_ADAPTER_CONTROL, atartns_6460976d-3415-4cda-b128-f74baefd075f.xml, irb/AtaAdapterControl, storage.ataadaptercontrol
req.header: irb.h
req.include-header: Irb.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDE_ADAPTER_CONTROL
 - irb/IDE_ADAPTER_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - irb.h
api_name:
 - IDE_ADAPTER_CONTROL
---

# IDE_ADAPTER_CONTROL callback function


## -description

The *AtaAdapterControl* miniport driver routine is called to perform Plug and Play (PnP) and Power Management operations on the HBA.

> [!NOTE]
> The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -parameters

### -param ControllerExtension

[in] A pointer to the controller extension.

### -param ControlAction

[in] One of five actions that the miniport driver must perform as defined in the following table.
  
| ControlAction | Parameters | Description |
| ------------- | ---------- | ----------- |
| IdeStart     | IDE_CONTROLLER_CONFIGURATION | Indicates that the adapter is being started. The miniport driver should update the member in the [**IDE_CONTROLLER_CONFIGURATION**](ns-irb-_ide_controller_configuration.md) structure. If it is required, the miniport driver could obtain its hardware resources from the **IDE_CONTROLLER_CONFIGURATION** structure. |
| IdeStop      | None | The miniport driver should stop using any resources that are allocated for this controller. Be aware that the port driver guarantees that all the channels that  are exposed by the adapter are stopped before it stops the adapter. |
| IdePowerUp   | None | Indicates that the adapter is being turned on. Anything that does not persist across a power cycle must be configured during IdePowerUp. |
| IdePowerDown | None | Indicates that the adapter is being turned off. |
| IdeVendorDefined | None | Indicates that the miniport driver should perform a vendor-defined control action. |

### -param Parameters

[in, out] Parameters associated with the given action.

## -returns

The miniport driver must return **TRUE** to acknowledge the completion of the requested action. A return value of **FALSE** indicates that the miniport driver was unable to complete the action successfully. A return value of **FALSE** for certain actions might cause the device installation to fail.

## -remarks

The port driver guarantees that there is no outstanding I/O on the adapter before it invokes the *AtaAdapterControl* routine.

## -see-also

[**IDE_CONTROLLER_CONFIGURATION**](ns-irb-_ide_controller_configuration.md)

