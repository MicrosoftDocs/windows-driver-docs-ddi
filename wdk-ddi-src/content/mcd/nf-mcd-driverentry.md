---
UID: NF:mcd.DriverEntry
title: DriverEntry function
author: windows-driver-content
description: The DriverEntry miniport driver routine is called when the miniport driver is loaded.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\driverentry.htm
old-project: storage
ms.assetid: f756e66b-7e66-4a27-9327-70608207d99b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , D, DriverEntry, DriverEntry routine [Storage Devices], E, atartns_b300b119-8261-4daf-8155-c9da17cb519a.xml, e, i, n, r, storage.driverentry, t, v, wdm/DriverEntry, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	DriverEntry
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# DriverEntry function


## -description


The <b><i>DriverEntry</i></b> miniport driver routine is called when the miniport driver is loaded.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
NTSTATUS DriverEntry(
  _In_ struct _DRIVER_OBJECT *DriverObject,
  _In_ PUNICODE_STRING       RegistryPath
);
````


## -parameters




### -param DriverObject [in]

A pointer to an opaque structure to be used as the first parameter when this routine calls the <a href="..\irb\nf-irb-ataportinitializeex.md">AtaPortInitializeEx</a> routine.


### -param RegistryPath [in]

A pointer to an opaque structure to be used as the second parameter when this routine calls the <a href="..\irb\nf-irb-ataportinitializeex.md">AtaPortInitializeEx</a> routine.


## -returns



The return values for this routine are recommended to mirror the return values of <a href="..\irb\nf-irb-ataportinitializeex.md">AtaPortInitializeEx</a>.




## -remarks



<b>DriverEntry</b> is the first function that is called in an ATA miniport driver. The ATA miniport driver must allocate an <a href="..\irb\ns-irb-_ide_controller_interface.md">IDE_CONTROLLER_INTERFACE</a> structure, initialize it, and send it to <a href="..\irb\nf-irb-ataportinitializeex.md">AtaPortInitializeEx</a>. The ATA miniport driver indicates its support for the channel interface by setting the ChannelExtensionSize and the <b><i>AtaChannelInitRoutine</i></b> entry point in the <b>IDE_CONTROLLER_INTERFACE</b> structure. This causes the ATA port driver to call the function that is specified in the <b><i>AtaChannelInitRoutine</i></b> field that has a ChannelExtension of size ChannelExtensionSize. The function is called one time for every NumberOfChannels specified in the ControllerConfiguration structure that are returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550140">AtaAdapterControl</a> when <b>AtaAdapterControl</b> handles an IdeStart action.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550140">AtaAdapterControl</a>



<a href="..\irb\nf-irb-ataportinitializeex.md">AtaPortInitializeEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DriverEntry routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

