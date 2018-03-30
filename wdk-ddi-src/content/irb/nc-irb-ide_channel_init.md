---
UID: NC:irb.IDE_CHANNEL_INIT
title: IDE_CHANNEL_INIT
author: windows-driver-content
description: The AtaChannelInitRoutine miniport driver routine initializes the miniport driver's channel interface.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\atachannelinitroutine.htm
old-project: storage
ms.assetid: c59f93cc-d182-4764-a207-0799e55c6cf6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaChannelInitRoutine, AtaChannelInitRoutine routine [Storage Devices], IDE_CHANNEL_INIT, atartns_7bbe3bef-24c7-4666-9b83-a29646d92f71.xml, irb/AtaChannelInitRoutine, storage.atachannelinitroutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	irb.h
api_name:
-	AtaChannelInitRoutine
product: Windows
targetos: Windows
req.typenames: IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS, IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS
---

# IDE_CHANNEL_INIT callback


## -description


The <b><i>AtaChannelInitRoutine</i></b> miniport driver routine initializes the miniport driver's channel interface.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the miniport driver channel extension.


### -param ChannelInterface [in, out]

A pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff559034">IDE_CHANNEL_INTERFACE</a>. 


### -param InitContext








#### - Context [in, out]

A pointer to the controller extension.


## -returns



<b><i>AtaChannelInitRoutine</i></b> returns <b>TRUE</b> if the initialization succeeded. It returns <b>FALSE</b> if the initialization failed. 




## -remarks



A vendor-supplied miniport driver that supports the channel interface must implement an <b><i>AtaChannelInitRoutine</i></b> routine to initialize the controller's channels. In particular, the <b><i>AtaChannelInitRoutine</i></b> routine must complete the initialization of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559034">IDE_CHANNEL_INTERFACE</a> structure. The following sequence describes how the miniport driver and the port driver interact to initialize a channel: 

<ol>
<li>
While in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine, the miniport driver calls the port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550167">AtaPortInitializeEx</a> library routine to launch the initialization of the controller and the miniport driver. 

</li>
<li>
If the miniport driver supports the channel interface, the <b><i>DriverEntry</i></b> routine must initialize the <b>AtaChannelInitRoutine</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559039">IDE_CONTROLLER_INTERFACE</a> to point to the miniport driver's <b><i>AtaChannelInitRoutine</i></b> routine.

</li>
<li>
The port driver calls the <b><i>AtaAdapterControl</i></b> routine by using control action IdeStart. <b><i>AtaChannelInitRoutine</i></b> is called one time for every NumberOfChannels specified in the ControllerConfiguration structure that is returned by the <b><i>AtaAdapterControl</i></b> routine when <b><i>AtaAdapterControl</i></b> handles an <b>IdeStart</b> action.

</li>
</ol>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550167">AtaPortInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559034">IDE_CHANNEL_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559039">IDE_CONTROLLER_INTERFACE</a>
 

 

