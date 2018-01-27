---
UID: NF:irb.AtaPortReadPortBufferUlong
title: AtaPortReadPortBufferUlong function
author: windows-driver-content
description: The AtaPortReadPortBufferUlong routine transfers a given number of ULONG values from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadportbufferulong.htm
old-project: storage
ms.assetid: ff70685f-f3cf-49c0-bb0b-02e561feeac3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortReadPortBufferUlong routine [Storage Devices], irb/AtaPortReadPortBufferUlong, AtaPortReadPortBufferUlong, storage.ataportreadportbufferulong, atartns_e2f251c9-d2a0-4b33-91d8-2d700eb4253e.xml
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
-	AtaPortReadPortBufferUlong
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortReadPortBufferUlong function


## -description


The <b>AtaPortReadPortBufferUlong</b> routine transfers a given number of ULONG values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID AtaPortReadPortBufferUlong(
  _In_ PULONG Port,
  _In_ PULONG Buffer,
  _In_ ULONG  Count
);
````


## -parameters




### -param Port [in]

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.


### -param Buffer [in]

A pointer to the destination buffer.


### -param Count [in]

Specifies the number of ULONG values to read from the HBA.


## -returns


None 



## -see-also

<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>

<a href="..\irb\nf-irb-ataportreadportbufferuchar.md">AtaPortReadPortBufferUchar</a>

<a href="..\irb\nf-irb-ataportreadportbufferushort.md">AtaPortReadPortBufferUshort</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortReadPortBufferUlong routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

