---
UID: NC:irb.IDE_CHANNEL_INIT
title: IDE_CHANNEL_INIT (irb.h)
description: The AtaChannelInitRoutine miniport driver routine initializes the miniport driver's channel interface.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\atachannelinitroutine.htm
tech.root: storage
ms.date: 08/26/2022
keywords: ["IDE_CHANNEL_INIT callback function"]
ms.keywords: AtaChannelInitRoutine, AtaChannelInitRoutine routine [Storage Devices], IDE_CHANNEL_INIT, atartns_7bbe3bef-24c7-4666-9b83-a29646d92f71.xml, irb/AtaChannelInitRoutine, storage.atachannelinitroutine
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
 - IDE_CHANNEL_INIT
 - irb/IDE_CHANNEL_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - irb.h
api_name:
 - IDE_CHANNEL_INIT
---

# IDE_CHANNEL_INIT callback function

## -description

The **AtaChannelInitRoutine** miniport driver routine initializes the miniport driver's channel interface.

> [!NOTE]
> The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -parameters

### -param ChannelExtension

[in] A pointer to the miniport driver channel extension.

### -param ChannelInterface

[in, out] Pointer to an [**IDE_CHANNEL_INTERFACE**](ns-irb-_ide_channel_interface.md) structure containing interface information for the indicated channel.

### -param InitContext

[in, out] A pointer to the controller extension.

## -returns

**AtaChannelInitRoutine** returns TRUE if the initialization succeeded. It returns FALSE if the initialization failed.

## -remarks

A vendor-supplied miniport driver that supports the channel interface must implement an **AtaChannelInitRoutine** routine to initialize the controller's channels. In particular, the **AtaChannelInitRoutine** routine must complete the initialization of the [**IDE_CHANNEL_INTERFACE**](ns-irb-_ide_channel_interface.md) structure. The following sequence describes how the miniport driver and the port driver interact to initialize a channel:

1. While in its [**DriverEntry**](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine, the miniport driver calls the port driver's [**AtaPortInitializeEx**](nf-irb-ataportinitializeex.md) library routine to launch the initialization of the controller and the miniport driver.

2. If the miniport driver supports the channel interface, the **DriverEntry** routine must initialize the **AtaChannelInitRoutine** member of [**IDE_CONTROLLER_INTERFACE**](ns-irb-_ide_controller_interface.md) to point to the miniport driver's **AtaChannelInitRoutine** routine.

3. The port driver calls the **AtaAdapterControl** routine by using control action IdeStart. **AtaChannelInitRoutine** is called one time for every NumberOfChannels specified in the ControllerConfiguration structure that is returned by the **AtaAdapterControl** routine when **AtaAdapterControl** handles an **IdeStart** action.

## -see-also

[**AtaPortInitializeEx**](nf-irb-ataportinitializeex.md)

[**IDE_CHANNEL_INTERFACE**](ns-irb-_ide_channel_interface.md)

[**IDE_CONTROLLER_INTERFACE**](ns-irb-_ide_controller_interface.md)
