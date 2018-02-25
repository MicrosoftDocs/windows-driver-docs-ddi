---
UID: NF:irb.AtaPortGetDeviceBase
title: AtaPortGetDeviceBase function
author: windows-driver-content
description: The AtaPortGetDeviceBase routine returns a mapped logical base address that is used to communicate with an HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportgetdevicebase.htm
old-project: storage
ms.assetid: 5cad43c7-00f0-4590-997c-f956afe07e55
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, AtaPortGetDeviceBase, AtaPortGetDeviceBase routine [Storage Devices], B, D, G, P, a, atartns_94ad1c8e-3a7b-4eeb-97d1-5b57284be6f3.xml, c, e, i, irb/AtaPortGetDeviceBase, o, r, s, storage.ataportgetdevicebase, t, v"
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
req.lib: Ataport.lib; Pciidex.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ataport.lib
-	ataport.dll
-	pciidex.lib
-	pciidex.dll
apiname:
-	AtaPortGetDeviceBase
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortGetDeviceBase function


## -description


The <b>AtaPortGetDeviceBase</b> routine returns a mapped logical base address that is used to communicate with an HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
PVOID AtaPortGetDeviceBase(
  _In_ PVOID                ChannelExtension,
  _In_ IDE_PHYSICAL_ADDRESS IoAddress,
  _In_ ULONG                NumberOfBytes
);
````


## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension.


### -param IoAddress [in]

Specifies the base address to map.


### -param NumberOfBytes [in]

Specifies the size, in bytes, of the range that the mappings should cover. The value for this parameter can be obtained from the <b>IdeAccessRange</b> member of the <a href="..\irb\ns-irb-_ide_miniport_resources.md">IDE_MINIPORT_RESOURCES</a> structure.


## -returns



<b>AtaPortGetDeviceBase</b> returns a mapped logical base address if the operation succeeds. Otherwise, it returns <b>NULL</b>. 




## -remarks



Miniport drivers must use logical addresses that have been mapped into system space by <b>AtaPortGetDeviceBase</b> instead of bus-relative addresses to communicate with its HBA. Calls to the <b>AtaPort...Port/Register</b><i>Xxx</i> routines require mapped logical addresses.




## -see-also

<a href="..\irb\nf-irb-ataportreadportulong.md">AtaPortReadPortUlong</a>



<a href="..\irb\nf-irb-ataportreadportushort.md">AtaPortReadPortUshort</a>



<a href="..\irb\nf-irb-ataportreadportuchar.md">AtaPortReadPortUchar</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortGetDeviceBase routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

