---
UID: NF:irb.AtaPortWriteRegisterBufferUchar
title: AtaPortWriteRegisterBufferUchar function
author: windows-driver-content
description: The AtaPortWriteRegisterBufferUchar routine transfers the indicated number of unsigned bytes from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteregisterbufferuchar.htm
old-project: storage
ms.assetid: 0b617fa4-da0b-4a98-a0e5-ad9fea67d980
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortWriteRegisterBufferUchar routine [Storage Devices], irb/AtaPortWriteRegisterBufferUchar, atartns_6722ff8e-9f8c-4b6a-88d1-305f892250bd.xml, AtaPortWriteRegisterBufferUchar, storage.ataportwriteregisterbufferuchar
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
-	AtaPortWriteRegisterBufferUchar
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortWriteRegisterBufferUchar function


## -description


The <b>AtaPortWriteRegisterBufferUchar</b> routine transfers the indicated number of unsigned bytes from a buffer to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID AtaPortWriteRegisterBufferUchar(
  _In_ PUCHAR Register,
  _In_ PUCHAR Buffer,
  _In_ ULONG  Count
);
````


## -parameters




### -param Register [in]

Contains the destination register address where the transfer should begin. This address value must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.


### -param Buffer [in]

A pointer to the source buffer.


### -param Count [in]

Specifies the number of unsigned bytes to write to the HBA.


## -returns


None 



## -see-also

<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>

<a href="..\irb\nf-irb-ataportwriteregisterbufferulong.md">AtaPortWriteRegisterBufferUlong</a>

<a href="..\irb\nf-irb-ataportwriteregisterbufferushort.md">AtaPortWriteRegisterBufferUshort</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortWriteRegisterBufferUchar routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

