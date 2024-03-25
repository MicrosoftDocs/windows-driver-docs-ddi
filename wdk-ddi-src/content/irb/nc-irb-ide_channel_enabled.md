---
UID: NC:irb.IDE_CHANNEL_ENABLED
title: IDE_CHANNEL_ENABLED (irb.h)
description: The AtaControllerChannelEnabled miniport driver routine indicates whether the specified channel is enabled.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\atacontrollerchannelenabled.htm
tech.root: storage
ms.date: 08/26/2022
keywords: ["IDE_CHANNEL_ENABLED callback function"]
ms.keywords: AtaControllerChannelEnabled, AtaControllerChannelEnabled routine [Storage Devices], IDE_CHANNEL_ENABLED, atartns_4beac2ec-b776-4af2-9acc-b236e0adc364.xml, irb/AtaControllerChannelEnabled, storage.atacontrollerchannelenabled
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
 - IDE_CHANNEL_ENABLED
 - irb/IDE_CHANNEL_ENABLED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - irb.h
api_name:
 - IDE_CHANNEL_ENABLED
---

# IDE_CHANNEL_ENABLED callback function

## -description

The **AtaControllerChannelEnabled** miniport driver routine indicates whether the specified channel is enabled.

> [!NOTE]
> The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -parameters

### -param ControllerExtension

[in] A pointer to the controller extension.

### -param Channel

[in] The channel to enable.

## -returns

**AtaControllerChannelEnabled** returns an enumerator value of type [**ATA_CHANNEL_STATE**](ne-irb-ata_channel_state.md), which can have any of the following values:

| Return code | Meaning |
| ----------- | ------- |
| ChannelStateEnabled  | Indicates that the specified channel is enabled. |
| ChannelStateDisabled | Indicates that the specified channel is disabled. |
| ChannelStateUnKnown  | Indicates that the state of the channel could not be determined.|

## -remarks

The following sequence describes how the miniport driver and the port driver interact to determine which controller channels are enabled:

1. The port driver calls the miniport driver's **AtaAdapterControl** routine with control action **IdeStart**.

2. While the miniport driver processes the **AtaAdapterControl** routine with control action **IdeStart**, it initializes the **NumberOfChannels** member of [**IDE_CONTROLLER_CONFIGURATION**](ns-irb-_ide_controller_configuration.md) to indicate the number of channels that are enabled.

3. After the **AtaAdapterControl** routine returns, the port driver calls **AtaControllerChannelEnabled** one time for every NumberOfChannels specified in the ControllerConfiguration structure that are returned by **AtaAdapterControl**.

This routine should not have steps that are critical to the operation of the controller. There are situations, such as during a crashdump operation, where this function will not be called at all.  Additionally, this function is not called when a channel is restarted, only when PCIIDEx responds to a QueryDeviceRelations IRP.

**AtaControllerChannelEnabled** is an optional routine. If the miniport driver does not implement this routine, the port driver will load a default handler. If the port driver loads a default handler, all channels that are specified by NumberOfChannels in the ControllerConfiguration structure that is returned by [**AtaAdapterControl**](nc-irb-ide_adapter_control.md) when handling an IdeStart action are assumed to be enabled. This routine enables PCIIDEx to load the ATA port driver for only the channels enabled. Doing this allows for sparse channel support (for example, channel 0, channel 1, channel 3, channel 4, and channel 6, but not channel 2 and channel 5).

## -see-also

[**IDE_CONTROLLER_CONFIGURATION**](ns-irb-_ide_controller_configuration.md)
