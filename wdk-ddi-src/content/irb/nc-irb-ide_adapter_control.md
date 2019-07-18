---
UID: NC:irb.IDE_ADAPTER_CONTROL
title: IDE_ADAPTER_CONTROL (irb.h)
description: The AtaAdapterControl miniport driver routine is called to perform Plug and Play (PnP) and Power Management operations on the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataadaptercontrol.htm
tech.root: storage
ms.assetid: 50125022-7450-4582-b98d-1d597e4e96d4
ms.date: 03/29/2018
ms.keywords: AtaAdapterControl, AtaAdapterControl routine [Storage Devices], IDE_ADAPTER_CONTROL, atartns_6460976d-3415-4cda-b128-f74baefd075f.xml, irb/AtaAdapterControl, storage.ataadaptercontrol
ms.topic: callback
f1_keywords:
 - "irb/AtaAdapterControl"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- irb.h
api_name:
- AtaAdapterControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDE_ADAPTER_CONTROL callback function


## -description


The <i>AtaAdapterControl</i> miniport driver routine is called to perform Plug and Play (PnP) and Power Management operations on the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ControllerExtension [in]

A pointer to the controller extension.


### -param ControlAction [in]


      One of five actions that the miniport driver must perform as defined in the following table.
  

<table>
<tr>
<th>ControlAction</th>
<th>Parameters</th>
<th>Description</th>
</tr>
<tr>
<td>
IdeStart

</td>
<td>
IDE_CONTROLLER_CONFIGURATION

</td>
<td>
Indicates that the adapter is being started. The miniport driver should update the member in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/ns-irb-_ide_controller_configuration">IDE_CONTROLLER_CONFIGURATION</a> structure. If it is required, the miniport driver could obtain its hardware resources from the <b>IDE_CONTROLLER_CONFIGURATION</b> structure.

</td>
</tr>
<tr>
<td>
IdeStop

</td>
<td>
None

</td>
<td>
The miniport driver should stop using any resources that are allocated for this controller. Be aware that the port driver guarantees that all the channels that  are exposed by the adapter are stopped before it stops the adapter.

</td>
</tr>
<tr>
<td>
IdePowerUp

</td>
<td>
None

</td>
<td>
Indicates that the adapter is being turned on. Anything that does not persist across a power cycle must be configured during IdePowerUp.  

</td>
</tr>
<tr>
<td>
IdePowerDown

</td>
<td>
None

</td>
<td>
Indicates that the adapter is being turned off.

</td>
</tr>
<tr>
<td>
IdeVendorDefined

</td>
<td>
None

</td>
<td>
Indicates that the miniport driver should perform a vendor-defined control action..

</td>
</tr>
</table>
 


### -param Parameters [in, out]

Parameters associated with the given action.


## -returns



The miniport driver must return <b>TRUE</b> to acknowledge the completion of the requested action. A return value of <b>FALSE</b> indicates that the miniport driver was unable to complete the action successfully. A return value of <b>FALSE</b> for certain actions might cause the device installation to fail.




## -remarks



The port driver guarantees that there is no outstanding I/O on the adapter before it invokes the <i>AtaAdapterControl</i> routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/ns-irb-_ide_controller_configuration">IDE_CONTROLLER_CONFIGURATION</a>
 

 

