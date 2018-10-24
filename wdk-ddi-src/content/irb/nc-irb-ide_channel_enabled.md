---
UID: NC:irb.IDE_CHANNEL_ENABLED
title: IDE_CHANNEL_ENABLED
author: windows-driver-content
description: The AtaControllerChannelEnabled miniport driver routine indicates whether the specified channel is enabled.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\atacontrollerchannelenabled.htm
tech.root: storage
ms.assetid: 67713537-6a5b-4108-8af9-fb5d16844b03
ms.date: 03/29/2018
ms.keywords: AtaControllerChannelEnabled, AtaControllerChannelEnabled routine [Storage Devices], IDE_CHANNEL_ENABLED, atartns_4beac2ec-b776-4af2-9acc-b236e0adc364.xml, irb/AtaControllerChannelEnabled, storage.atacontrollerchannelenabled
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
-	AtaControllerChannelEnabled
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDE_CHANNEL_ENABLED callback function


## -description


The <b><i>AtaControllerChannelEnabled</i></b> miniport driver routine indicates whether the specified channel is enabled.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ControllerExtension [in]

A pointer to the controller extension.


### -param Channel








#### - ChannelNumber [in]

Specifies the channel number whose state will be determined. 


## -returns



<b><i>AtaControllerChannelEnabled</i></b> returns an enumerator value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551308">ATA_CHANNEL_STATE</a>, which can have any of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ChannelStateEnabled</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the specified channel is enabled. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ChannelStateDisabled</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the specified channel is disabled.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ChannelStateUnKnown</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the state of the channel could not be determined.

</td>
</tr>
</table>
 




## -remarks



The following sequence describes how the miniport driver and the port driver interact to determine which controller channels are enabled:

<ol>
<li>
The port driver calls the miniport driver's <b><i>AtaAdapterControl</i></b> routine with control action <b>IdeStart</b>. 

</li>
<li>
While the miniport driver processes the <b><i>AtaAdapterControl</i></b> routine with control action <b>IdeStart</b>, it initializes the <b>NumberOfChannels</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559036">IDE_CONTROLLER_CONFIGURATION</a> to indicate the number of channels that are enabled. 

</li>
<li>
After the <b><i>AtaAdapterControl</i></b> routine returns, the port driver calls <b>AtaControllerChannelEnabled</b> one time for every NumberOfChannels specified in the ControllerConfiguration structure that are returned by <b><i>AtaAdapterControl</i></b>.

</li>
</ol>
This routine should not have steps that are critical to the operation of the controller. There are situations, such as during a crashdump operation, where this function will not be called at all.  Additionally, this function is not called when a channel is restarted, only when PCIIDEx responds to a QueryDeviceRelations IRP.

<b>AtaControllerChannelEnabled</b> is an optional routine. If the miniport driver does not implement this routine, the port driver will load a default handler. If the port driver loads a default handler, all channels that are specified by NumberOfChannels in the ControllerConfiguration structure that is returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550140">AtaAdapterControl</a> when handling an IdeStart action are assumed to be enabled. This routine enables PCIIDEx to load the ATA port driver for only the channels enabled. Doing this allows for sparse channel support (for example, channel 0, channel 1, channel 3, channel 4, and channel 6, but not channel 2 and channel 5).




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559036">IDE_CONTROLLER_CONFIGURATION</a>
 

 

