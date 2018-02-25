---
UID: NF:irb.AtaPortReadPortUlong
title: AtaPortReadPortUlong function
author: windows-driver-content
description: The AtaPortReadPortUlong routine reads a ULONG value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadportulong.htm
old-project: storage
ms.assetid: f9e5fb0a-7add-462c-9b2a-2b543f7c7649
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, AtaPortReadPortUlong, AtaPortReadPortUlong routine [Storage Devices], P, R, U, a, atartns_e2d91111-cf48-4987-82ff-055469d67dc8.xml, d, e, g, irb/AtaPortReadPortUlong, l, n, o, r, storage.ataportreadportulong, t"
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
-	AtaPortReadPortUlong
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortReadPortUlong function


## -description


The <b>AtaPortReadPortUlong</b> routine reads a ULONG value from the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
ULONG AtaPortReadPortUlong(
  _In_ PULONG Port
);
````


## -parameters




### -param Port [in]

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.


## -returns



<b>AtaPortReadPortUlong</b> returns a ULONG value from the HBA's I/O port. 




## -see-also

<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>



<a href="..\irb\nf-irb-ataportreadportushort.md">AtaPortReadPortUshort</a>



<a href="..\irb\nf-irb-ataportreadportuchar.md">AtaPortReadPortUchar</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortReadPortUlong routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

