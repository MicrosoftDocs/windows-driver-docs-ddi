---
UID: NF:irb.AtaPortReadPortBufferUchar
title: AtaPortReadPortBufferUchar function
author: windows-driver-content
description: The AtaPortReadPortBufferUchar routine transfers a given number of unsigned byte values from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadportbufferuchar.htm
old-project: storage
ms.assetid: 7bb8ed1d-fc6c-4475-9770-603be930be7a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaPortReadPortBufferUchar, AtaPortReadPortBufferUchar routine [Storage Devices], atartns_1c072aa8-585a-4f8c-be16-be8c1dbc6258.xml, irb/AtaPortReadPortBufferUchar, storage.ataportreadportbufferuchar
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
-	AtaPortReadPortBufferUchar
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortReadPortBufferUchar function


## -description


The <b>AtaPortReadPortBufferUchar</b> routine transfers a given number of unsigned byte values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID AtaPortReadPortBufferUchar(
  _In_ PUCHAR Port,
  _In_ PUCHAR Buffer,
  _In_ ULONG  Count
);
````


## -parameters




### -param Port [in]

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.


### -param Buffer [in]

A pointer to the destination buffer.


### -param Count [in]

Specifies the number of bytes to read from the HBA.


## -returns



None 




## -see-also

<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>



<a href="..\irb\nf-irb-ataportreadportbufferulong.md">AtaPortReadPortBufferUlong</a>



<a href="..\irb\nf-irb-ataportreadportbufferushort.md">AtaPortReadPortBufferUshort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortReadPortBufferUchar routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

