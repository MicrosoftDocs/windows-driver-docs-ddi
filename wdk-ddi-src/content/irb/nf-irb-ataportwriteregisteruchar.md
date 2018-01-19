---
UID: NF:irb.AtaPortWriteRegisterUchar
title: AtaPortWriteRegisterUchar function
author: windows-driver-content
description: The AtaPortWriteRegisterUchar routine transfers an unsigned byte to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteregisteruchar.htm
old-project: storage
ms.assetid: c7c887e6-6861-4366-b8b4-fe6292ac5c99
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortWriteRegisterUchar
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
req.alt-api: AtaPortWriteRegisterUchar
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

# AtaPortWriteRegisterUchar function



## -description
The <b>AtaPortWriteRegisterUchar</b> routine transfers an unsigned byte to the HBA.



## -syntax

````
VOID AtaPortWriteRegisterUchar(
  _In_ PUCHAR Register,
  _In_ UCHAR  Value
);
````


## -parameters

### -param Register [in]

A pointer to the destination register. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.


### -param Value [in]

Specifies the value to write to the register for the HBA.


## -returns
None 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>
</dt>
<dt>
<a href="..\irb\nf-irb-ataportwriteregisterulong.md">AtaPortWriteRegisterUlong</a>
</dt>
<dt>
<a href="..\irb\nf-irb-ataportwriteregisterushort.md">AtaPortWriteRegisterUshort</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortWriteRegisterUchar routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

