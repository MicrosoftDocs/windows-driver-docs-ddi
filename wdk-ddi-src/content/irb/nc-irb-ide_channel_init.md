---
UID: NC:irb.IDE_CHANNEL_INIT
title: IDE_CHANNEL_INIT
author: windows-driver-content
description: The AtaChannelInitRoutine miniport driver routine initializes the miniport driver's channel interface.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\atachannelinitroutine.htm
old-project: storage
ms.assetid: c59f93cc-d182-4764-a207-0799e55c6cf6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: WdmlibIoGetAffinityInterrupt
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
req.alt-api: AtaChannelInitRoutine
req.alt-loc: irb.h
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
req.typenames: LUID
---

# IDE_CHANNEL_INIT callback



## -description
The <b><i>AtaChannelInitRoutine</i></b> miniport driver routine initializes the miniport driver's channel interface.



## -prototype

````
IDE_CHANNEL_INIT AtaChannelInitRoutine;

BOOLEAN AtaChannelInitRoutine(
  _In_    PVOID                  ChannelExtension,
  _Inout_ PIDE_CHANNEL_INTERFACE ChannelInterface,
  _Inout_ PVOID                  Context
)
{ ... }
````


## -parameters

### -param ChannelExtension [in]

A pointer to the miniport driver channel extension.


### -param ChannelInterface [in, out]

A pointer to a structure of type <a href="..\irb\ns-irb-_ide_channel_interface.md">IDE_CHANNEL_INTERFACE</a>. 


### -param Context [in, out]

A pointer to the controller extension.


## -returns
<b><i>AtaChannelInitRoutine</i></b> returns <b>TRUE</b> if the initialization succeeded. It returns <b>FALSE</b> if the initialization failed. 


## -remarks
A vendor-supplied miniport driver that supports the channel interface must implement an <b><i>AtaChannelInitRoutine</i></b> routine to initialize the controller's channels. In particular, the <b><i>AtaChannelInitRoutine</i></b> routine must complete the initialization of the <a href="..\irb\ns-irb-_ide_channel_interface.md">IDE_CHANNEL_INTERFACE</a> structure. The following sequence describes how the miniport driver and the port driver interact to initialize a channel: 

While in its <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine, the miniport driver calls the port driver's <a href="..\irb\nf-irb-ataportinitializeex.md">AtaPortInitializeEx</a> library routine to launch the initialization of the controller and the miniport driver. 

If the miniport driver supports the channel interface, the <b><i>DriverEntry</i></b> routine must initialize the <b>AtaChannelInitRoutine</b> member of <a href="..\irb\ns-irb-_ide_controller_interface.md">IDE_CONTROLLER_INTERFACE</a> to point to the miniport driver's <b><i>AtaChannelInitRoutine</i></b> routine.

The port driver calls the <b><i>AtaAdapterControl</i></b> routine by using control action IdeStart. <b><i>AtaChannelInitRoutine</i></b> is called one time for every NumberOfChannels specified in the ControllerConfiguration structure that is returned by the <b><i>AtaAdapterControl</i></b> routine when <b><i>AtaAdapterControl</i></b> handles an <b>IdeStart</b> action.


## -see-also
<dl>
<dt>
<a href="..\irb\nf-irb-ataportinitializeex.md">AtaPortInitializeEx</a>
</dt>
<dt>
<a href="..\irb\ns-irb-_ide_channel_interface.md">IDE_CHANNEL_INTERFACE</a>
</dt>
<dt>
<a href="..\irb\ns-irb-_ide_controller_interface.md">IDE_CONTROLLER_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaChannelInitRoutine routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

