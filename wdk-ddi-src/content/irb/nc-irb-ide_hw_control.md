---
UID: NC:irb.IDE_HW_CONTROL
title: IDE_HW_CONTROL
author: windows-driver-content
description: The IdeHwControl miniport driver routine notifies the miniport driver about Plug and Play (PnP) and power events.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\idehwcontrol.htm
old-project: storage
ms.assetid: 53f85f8d-3b50-4cfe-8bdd-d41d8c057f3e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDE_HW_CONTROL, IdeHwControl, IdeHwControl routine [Storage Devices], atartns_9c868c08-5470-4940-9067-0aa8a796b191.xml, irb/IdeHwControl, storage.idehwcontrol
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
-	IdeHwControl
product: Windows
targetos: Windows
req.typenames: LUID
---

# IDE_HW_CONTROL callback


## -description


The <i>IdeHwControl</i> miniport driver routine notifies the miniport driver about Plug and Play (PnP) and power events.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -prototype


````
IDE_HW_CONTROL IdeHwControl;

BOOLEAN IdeHwControl(
  _In_    PVOID              ChannelExtension,
  _In_    IDE_CONTROL_ACTION ControlAction,
  _Inout_ PVOID              Parameters
)
{ ... }
````


## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension.


### -param ControlAction [in]

Contains an enumerator value of type <a href="..\irb\ne-irb-ide_control_action.md">IDE_CONTROL_ACTION</a> that indicates the control action to perform. 


### -param Parameters [in, out]

A pointer to a buffer that contains the parameters that are associated with the control action. This parameter can have one of the values in the following table.

<table>
<tr>
<th>Control action</th>
<th>Parameters</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>IdeStart</b>

</td>
<td>
Parameter points to a structure of type IDE_CHANNEL_CONFIGURATION.

</td>
<td>
Indicates that the port driver is starting the channel.

</td>
</tr>
<tr>
<td>
<b>IdeVendorDefined</b>

</td>
<td>
Parameter points to a structure of type IDE_VENDOR_DEFINED_POWER_INFO.

</td>
<td>
Indicates that there is a vendor defined power event coming.

</td>
</tr>
</table>
 


## -returns



<i>IdeHwControl</i> returns <b>TRUE</b> if the operation was successful. Otherwise, it returns <b>FALSE</b>. 




## -remarks



The port driver makes sure that there is no outstanding I/O on the channel before it invokes this routine. The miniport driver can have its own power policy methods when the system enters a different power state. In order to achieve this, the miniport driver needs to do the following:

<ul>
<li>
Add a power policy setting scheme into the miniport driver's INF file. A GUID is needed to present a miniport driver-defined power policy. For more information about the power settings directive, see <a href="https://msdn.microsoft.com/0231ba90-5de4-4f5a-83bb-0f73be4b23ae">INF AddPowerSetting Directive</a>. More information about the GUIDs can be found at <a href="https://msdn.microsoft.com/library/windows/hardware/mt608265">Disk settings</a>.

</li>
<li>When the miniport driver routine <i>IdeHwControl</i> is called with control action <b>IdeStart</b>:<dl>
<dd>Check the SupportedAdvances.AdvancedChannelConfigurationSupported field in the ChannelConfiguration structure.</dd>
<dd>Check the AdvancedChannelConfiguration-&gt;Present.VendorDefinedPower field in the ChannelConfiguration structure.</dd>
<dd>If the values of the two fields listed previously are both <b>TRUE</b>, this version of the ATA port driver supports vendor-defined power management.</dd>
<dd>If vendor-defined power management is supported by the ATA port driver, the miniport driver can register for special power management handling by setting the AdvancedChannelConfiguration-&gt;VendorDefinedPower.ValidGuids and AdvancedChannelConfiguration-&gt;VendorDefinedPower.Guid[] fields (the latter should be the GUID of the power policy in the miniport driver's INF file).</dd>
</dl>
</li>
<li>
After vendor-defined power management is registered, the miniport driver will be able to receive calls to its <i>IdeHwControl</i> routine with control action <b>IdeVendorDefined</b> when the system power scheme changes.

</li>
<li>While the miniport driver processes the <i>IdeHwControl</i> routine with control action <b>IdeVendorDefined</b>, it should do following:<dl>
<dd>Compare the <b>SettingGuid</b> field from the parameter field of structure IDE_VENDOR_DEFINED_POWER_INFO with the GUID that the miniport driver registered to make sure that the call is for this channel. If the GUIDs do not match, the miniport driver should complete the call and take no action.</dd>
<dd>Get the <b>Value</b> field from the parameter field of structure IDE_VENDOR_DEFINED_POWER_INFO and perform the appropriate miniport driver-specific power management action.</dd>
</dl>
</li>
</ul>



## -see-also

<a href="..\irb\nf-irb-ataportgetuncachedextension.md">AtaPortGetUncachedExtension</a>



 

 


