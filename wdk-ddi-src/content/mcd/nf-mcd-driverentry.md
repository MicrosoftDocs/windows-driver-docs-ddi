---
UID: NF:mcd.DriverEntry
title: DriverEntry function (mcd.h)
description: The DriverEntry miniport driver routine is called when the miniport driver is loaded.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\driverentry.htm
tech.root: storage
ms.assetid: f756e66b-7e66-4a27-9327-70608207d99b
ms.date: 03/29/2018
keywords: ["DriverEntry function"]
ms.keywords: DriverEntry, DriverEntry routine [Storage Devices], atartns_b300b119-8261-4daf-8155-c9da17cb519a.xml, storage.driverentry, wdm/DriverEntry
f1_keywords:
 - "mcd/DriverEntry"
 - "DriverEntry"
req.header: mcd.h
req.include-header: Ntddk.h, Mcd.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- DriverEntry
targetos: Windows
req.typenames: 
---

# DriverEntry function


## -description


The <b><i>DriverEntry</i></b> miniport driver routine is called when the miniport driver is loaded.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param DriverObject [in]

A pointer to an opaque structure to be used as the first parameter when this routine calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportinitializeex">AtaPortInitializeEx</a> routine.


### -param RegistryPath [in]

A pointer to an opaque structure to be used as the second parameter when this routine calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportinitializeex">AtaPortInitializeEx</a> routine.


## -returns



The return values for this routine are recommended to mirror the return values of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportinitializeex">AtaPortInitializeEx</a>.




## -remarks



<b>DriverEntry</b> is the first function that is called in an ATA miniport driver. The ATA miniport driver must allocate an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ide_controller_interface">IDE_CONTROLLER_INTERFACE</a> structure, initialize it, and send it to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportinitializeex">AtaPortInitializeEx</a>. The ATA miniport driver indicates its support for the channel interface by setting the ChannelExtensionSize and the <b><i>AtaChannelInitRoutine</i></b> entry point in the <b>IDE_CONTROLLER_INTERFACE</b> structure. This causes the ATA port driver to call the function that is specified in the <b><i>AtaChannelInitRoutine</i></b> field that has a ChannelExtension of size ChannelExtensionSize. The function is called one time for every NumberOfChannels specified in the ControllerConfiguration structure that are returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_adapter_control">AtaAdapterControl</a> when <b>AtaAdapterControl</b> handles an IdeStart action.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_adapter_control">AtaAdapterControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportinitializeex">AtaPortInitializeEx</a>
 

 

