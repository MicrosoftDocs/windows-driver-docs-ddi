---
UID: NF:irb.AtaPortWriteRegisterUlong
title: AtaPortWriteRegisterUlong function
author: windows-driver-content
description: The AtaPortWriteRegisterUlong routine transfers a ULONG value to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteregisterulong.htm
old-project: storage
ms.assetid: 62abbee8-cd62-4106-9a7e-c93bfc916769
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortWriteRegisterUlong
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
req.alt-api: AtaPortWriteRegisterUlong
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

# AtaPortWriteRegisterUlong function



## -description
The <b>AtaPortWriteRegisterUlong</b> routine transfers a ULONG value to the HBA.



## -syntax

````
VOID AtaPortWriteRegisterUlong(
  _In_ PULONG Register,
  _In_ ULONG  Value
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
<a href="..\irb\nf-irb-ataportwriteregisteruchar.md">AtaPortWriteRegisterUchar</a>
</dt>
<dt>
<a href="..\irb\nf-irb-ataportwriteregisterushort.md">AtaPortWriteRegisterUshort</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortWriteRegisterUlong routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

