---
UID: NF:irb.AtaPortInitializeEx
title: AtaPortInitializeEx function (irb.h)
description: The AtaPortInitializeEx ATA port driver library routine initializes the port and miniport drivers.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportinitializeex.htm
tech.root: storage
ms.assetid: 578992cf-63eb-4b8e-b0cb-9caee5c534e1
ms.date: 03/29/2018
keywords: ["AtaPortInitializeEx function"]
ms.keywords: AtaPortInitializeEx, AtaPortInitializeEx routine [Storage Devices], atartns_dab74a62-5788-4de9-91eb-e1eb7a7bcaf5.xml, irb/AtaPortInitializeEx, storage.ataportinitializeex
f1_keywords:
 - "irb/AtaPortInitializeEx"
req.header: irb.h
req.include-header: Ata.h, Irb.h
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
req.lib: Pciidex.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Pciidex.lib
- Pciidex.dll
api_name:
- AtaPortInitializeEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortInitializeEx function


## -description


The <b>AtaPortInitializeEx</b> ATA port driver library routine initializes the port and miniport drivers.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param DriverObject [in]

A pointer to the miniport driver object.


### -param RegistryPath [in]

Contains a Unicode string that indicates the location in the registry where the miniport driver configuration information is stored.


### -param ControllerInterface [in]

Contains the entry points for the <b><i>AtaAdapterControl</i></b>, <b><i>AtaChannelInitRoutine</i></b>, <b><i>AtaControllerChannelEnabled</i></b>, and <b><i>AtaControllerTransferModeSelect</i></b> routines.


## -returns



<b>AtaPortInitializeEx</b> returns STATUS_SUCCESS if the operation succeeds.  Otherwise, it returns an error code. 




## -remarks



The <b>AtaPortInitializeEx</b> routine initializes key data structures that are used by the port and miniport drivers. It also starts the initialization of the controller's channels. The following sequence describes the principal actions taken by this routine:

<ol>
<li>While in its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine, the miniport driver calls the port driver's <b>AtaPortInitializeEx</b> library routine and passes it the following key parameters: <ul>
<li><i>ControllerInterface</i>: Contains the entry points for the <b><i>AtaAdapterControl</i></b>, <b><i>AtaChannelInitRoutine</i></b>, <b><i>AtaControllerChannelEnabled</i></b>, and <b><i>AtaControllerTransferModeSelect</i></b> routines.</li>
</ul>
</li>
<li>The <b>AtaPortInitializeEx</b> routine initializes key data structures that are used by the port and miniport drivers and performs the following actions:<ol>
<li>Initializes the miniport driver's dispatch tables.</li>
<li>Allocates an extension for the driver object. </li>
<li>Copies ControllerInterface into the driver extension.</li>
<li>After <b><i>AtaPortInitializeEx</i></b> completes the initialization of the port driver, it returns to the miniport driver's <b><i>DriverEntry</i></b> routine.</li>
</ol>
</li>
<li>
While starting the adapter device, the miniport driver routine <b><i>AtaAdapterControl</i></b> will be called by the port driver with control action <b>IdeStart</b>.

</li>
<li>
When the ATA port driver is processing a channel device start request, the miniport driver routine <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_channel_enabled">AtaControllerChannelEnabled</a> is called for each channel on the controller to determine whether it is enabled.

</li>
<li>
After the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_channel_enabled">AtaControllerChannelEnabled</a> routine determines which channels are enabled, the ATA port driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_channel_init">AtaChannelInitRoutine</a> for this channel. 

</li>
</ol>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_channel_init">AtaChannelInitRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_channel_enabled">AtaControllerChannelEnabled</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ide_controller_configuration">IDE_CONTROLLER_CONFIGURATION</a>
 

 

