---
UID: NF:irb.AtaPortReadPortUchar
title: AtaPortReadPortUchar function
author: windows-driver-content
description: The AtaPortReadPortUchar routine reads an unsigned byte value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadportuchar.htm
old-project: storage
ms.assetid: 9be74e98-ba68-492c-9660-43b2f76052cd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaPortReadPortUchar, AtaPortReadPortUchar routine [Storage Devices], atartns_6ac346ce-b2cd-4c50-b55f-1c952a01e736.xml, irb/AtaPortReadPortUchar, storage.ataportreadportuchar
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
-	AtaPortReadPortUchar
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortReadPortUchar function


## -description


The <b>AtaPortReadPortUchar</b> routine reads an unsigned byte value from the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
UCHAR AtaPortReadPortUchar(
  _In_ PUCHAR Port
);
````


## -parameters




### -param Port [in]

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.


## -returns



<b>AtaPortReadPortUchar</b> returns a UCHAR value from the HBA's I/O port. 




## -see-also

<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>



<a href="..\irb\nf-irb-ataportreadportulong.md">AtaPortReadPortUlong</a>



<a href="..\irb\nf-irb-ataportreadportushort.md">AtaPortReadPortUshort</a>



 

 


