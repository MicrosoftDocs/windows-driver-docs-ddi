---
UID: NF:irb.AtaPortReadPortUshort
title: AtaPortReadPortUshort function
author: windows-driver-content
description: The AtaPortReadPortUshort routine reads a USHORT value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadportushort.htm
old-project: storage
ms.assetid: e2534e79-293e-41db-b874-3f39aa5af864
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortReadPortUshort
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
req.alt-api: AtaPortReadPortUshort
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

# AtaPortReadPortUshort function



## -description
The <b>AtaPortReadPortUshort</b> routine reads a USHORT value from the HBA.



## -syntax

````
USHORT AtaPortReadPortUshort(
  _In_ PUSHORT Port
);
````


## -parameters

### -param Port [in]

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.


## -returns
<b>AtaPortReadPortUshort</b> returns a USHORT value from the HBA's I/O port. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>
</dt>
<dt>
<a href="..\irb\nf-irb-ataportreadportuchar.md">AtaPortReadPortUchar</a>
</dt>
<dt>
<a href="..\irb\nf-irb-ataportreadportulong.md">AtaPortReadPortUlong</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortReadPortUshort routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

