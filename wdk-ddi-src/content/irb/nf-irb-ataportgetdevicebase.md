---
UID: NF:irb.AtaPortGetDeviceBase
title: AtaPortGetDeviceBase function
author: windows-driver-content
description: The AtaPortGetDeviceBase routine returns a mapped logical base address that is used to communicate with an HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportgetdevicebase.htm
old-project: storage
ms.assetid: 5cad43c7-00f0-4590-997c-f956afe07e55
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortGetDeviceBase, AtaPortGetDeviceBase routine [Storage Devices], atartns_94ad1c8e-3a7b-4eeb-97d1-5b57284be6f3.xml, irb/AtaPortGetDeviceBase, storage.ataportgetdevicebase
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ataport.lib
-	ataport.dll
-	pciidex.lib
-	pciidex.dll
api_name:
-	AtaPortGetDeviceBase
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortGetDeviceBase function


## -description


The <b>AtaPortGetDeviceBase</b> routine returns a mapped logical base address that is used to communicate with an HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension.


### -param IoAddress [in]

Specifies the base address to map.


### -param NumberOfBytes [in]

Specifies the size, in bytes, of the range that the mappings should cover. The value for this parameter can be obtained from the <b>IdeAccessRange</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559119">IDE_MINIPORT_RESOURCES</a> structure.


## -returns



<b>AtaPortGetDeviceBase</b> returns a mapped logical base address if the operation succeeds. Otherwise, it returns <b>NULL</b>. 




## -remarks



Miniport drivers must use logical addresses that have been mapped into system space by <b>AtaPortGetDeviceBase</b> instead of bus-relative addresses to communicate with its HBA. Calls to the <b>AtaPort...Port/Register</b><i>Xxx</i> routines require mapped logical addresses.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550182">AtaPortReadPortUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550184">AtaPortReadPortUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550185">AtaPortReadPortUshort</a>
 

 

