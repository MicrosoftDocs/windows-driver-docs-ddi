---
UID: NF:irb.AtaPortWritePortUchar
title: AtaPortWritePortUchar function
author: windows-driver-content
description: The AtaPortWritePortUchar routine transfers an unsigned byte to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteportuchar.htm
old-project: storage
ms.assetid: 2585da94-babe-479f-8957-adaa9190451e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaPortWritePortUchar, AtaPortWritePortUchar routine [Storage Devices], atartns_25e284e4-0c1e-4172-b0d2-4435e23f7270.xml, irb/AtaPortWritePortUchar, storage.ataportwriteportuchar
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
-	AtaPortWritePortUchar
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortWritePortUchar function


## -description


The <b>AtaPortWritePortUchar</b> routine transfers an unsigned byte to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID AtaPortWritePortUchar(
  _In_ PUCHAR Port,
  _In_ UCHAR  Value
);
````


## -parameters




### -param Port [in]

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.


### -param Value [in]

Specifies the value to write to the HBA's I/O port


## -returns



None 




## -see-also

<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>



<a href="..\irb\nf-irb-ataportwriteportulong.md">AtaPortWritePortUlong</a>



<a href="..\irb\nf-irb-ataportwriteportushort.md">AtaPortWritePortUshort</a>



 

 


