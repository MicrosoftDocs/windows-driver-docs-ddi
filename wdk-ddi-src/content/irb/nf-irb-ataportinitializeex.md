---
UID: NF:irb.AtaPortInitializeEx
title: AtaPortInitializeEx function
author: windows-driver-content
description: The AtaPortInitializeEx ATA port driver library routine initializes the port and miniport drivers.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportinitializeex.htm
old-project: storage
ms.assetid: 578992cf-63eb-4b8e-b0cb-9caee5c534e1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , A, AtaPortInitializeEx, AtaPortInitializeEx routine [Storage Devices], E, I, P, a, atartns_dab74a62-5788-4de9-91eb-e1eb7a7bcaf5.xml, e, i, irb/AtaPortInitializeEx, l, n, o, r, storage.ataportinitializeex, t, x, z"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Pciidex.lib
-	Pciidex.dll
apiname:
-	AtaPortInitializeEx
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortInitializeEx function


## -description


The <b>AtaPortInitializeEx</b> ATA port driver library routine initializes the port and miniport drivers.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
ULONG AtaPortInitializeEx(
  _In_ PVOID                     DriverObject,
  _In_ PVOID                     RegistryPath,
  _In_ PIDE_CONTROLLER_INTERFACE ControllerInterface
);
````


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
<li>While in its <a href="..\mcd\nf-mcd-driverentry.md">DriverEntry</a> routine, the miniport driver calls the port driver's <b>AtaPortInitializeEx</b> library routine and passes it the following key parameters: <ul>
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
When the ATA port driver is processing a channel device start request, the miniport driver routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff550142">AtaControllerChannelEnabled</a> is called for each channel on the controller to determine whether it is enabled.

</li>
<li>
After the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550142">AtaControllerChannelEnabled</a> routine determines which channels are enabled, the ATA port driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550141">AtaChannelInitRoutine</a> for this channel. 

</li>
</ol>



## -see-also

<a href="..\irb\ns-irb-_ide_controller_configuration.md">IDE_CONTROLLER_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550141">AtaChannelInitRoutine</a>



<a href="..\mcd\nf-mcd-driverentry.md">DriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550142">AtaControllerChannelEnabled</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortInitializeEx routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

