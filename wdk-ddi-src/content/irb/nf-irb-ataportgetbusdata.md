---
UID: NF:irb.AtaPortGetBusData
title: AtaPortGetBusData function
author: windows-driver-content
description: The AtaPortGetBusData routine retrieves data from the location that is specified by ConfigDataOffset within the device's PCI configuration space.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportgetbusdata.htm
tech.root: storage
ms.assetid: bfff10ab-7e15-4db3-b808-947d61844bc0
ms.date: 3/29/2018
ms.keywords: AtaPortGetBusData, AtaPortGetBusData routine [Storage Devices], atartns_a137d697-85fa-4d99-964f-94e9bcbb6b7b.xml, irb/AtaPortGetBusData, storage.ataportgetbusdata
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Pciidex.lib
-	Pciidex.dll
api_name:
-	AtaPortGetBusData
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortGetBusData function


## -description


The <b>AtaPortGetBusData</b> routine retrieves data from the location that is specified by <i>ConfigDataOffset</i> within the device's PCI configuration space.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ControllerExtension [in]

A pointer to the HBA controller extension.


### -param Buffer [in]

A pointer to the buffer where the retrieved data is returned. 


### -param ConfigDataOffset [in]

Specifies an offset into the device's PCI bus configuration space where the return value is found.


### -param BufferLength [in]

Specifies the length, in bytes, of the buffer.


## -returns



<b>AtaPortGetBusData</b> returns the amount of the retrieved data in bytes.




## -remarks



<b>AtaPortGetBusData</b> retrieves data from the specified offset in the device's PCI bus configuration space and returns it in the buffer that is provided.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550232">AtaPortSetBusData</a>
 

 

