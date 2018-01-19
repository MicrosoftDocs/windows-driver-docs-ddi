---
UID: NF:irb.AtaPortWritePortUchar
title: AtaPortWritePortUchar function
author: windows-driver-content
description: The AtaPortWritePortUchar routine transfers an unsigned byte to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteportuchar.htm
old-project: storage
ms.assetid: 2585da94-babe-479f-8957-adaa9190451e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortWritePortUchar
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
req.alt-api: AtaPortWritePortUchar
req.alt-loc: ataport.lib,ataport.dll,pciidex.lib,pciidex.dll
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
req.typenames: IDE_POWER_STATE
---

# AtaPortWritePortUchar function



## -description
The <b>AtaPortWritePortUchar</b> routine transfers an unsigned byte to the HBA.



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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>
</dt>
<dt>
<a href="..\irb\nf-irb-ataportwriteportushort.md">AtaPortWritePortUshort</a>
</dt>
<dt>
<a href="..\irb\nf-irb-ataportwriteportulong.md">AtaPortWritePortUlong</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortWritePortUchar routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

