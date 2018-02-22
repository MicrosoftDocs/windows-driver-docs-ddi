---
UID: NF:irb.AtaPortWriteRegisterBufferUshort
title: AtaPortWriteRegisterBufferUshort function
author: windows-driver-content
description: The AtaPortWriteRegisterBufferUshort routine transfers the indicated number of USHORT values from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteregisterbufferushort.htm
old-project: storage
ms.assetid: 1de586c7-2fee-488d-a84e-7cc08165ad50
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: atartns_7b2b3f11-f9ae-45a0-a690-9f879bd6e478.xml, AtaPortWriteRegisterBufferUshort, storage.ataportwriteregisterbufferushort, AtaPortWriteRegisterBufferUshort routine [Storage Devices], irb/AtaPortWriteRegisterBufferUshort
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
-	AtaPortWriteRegisterBufferUshort
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortWriteRegisterBufferUshort function


## -description


The <b>AtaPortWriteRegisterBufferUshort</b> routine transfers the indicated number of USHORT values from a buffer to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID AtaPortWriteRegisterBufferUshort(
  _In_ PUSHORT Register,
  _In_ PUSHORT Buffer,
  _In_ ULONG   Count
);
````


## -parameters




### -param Register [in]

Contains the destination register address where the transfer should begin. This address value must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.


### -param Buffer [in]

A pointer to the source buffer.


### -param Count [in]

Specifies the number of USHORT values to write to the HBA.


## -returns



None 




## -see-also

<a href="..\irb\nf-irb-ataportwriteregisterbufferushort.md">AtaPortWriteRegisterBufferUshort</a>



<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>



<a href="..\irb\nf-irb-ataportwriteregisterbufferuchar.md">AtaPortWriteRegisterBufferUchar</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortWriteRegisterBufferUshort routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

