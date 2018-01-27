---
UID: NF:irb.AtaPortReadRegisterUchar
title: AtaPortReadRegisterUchar function
author: windows-driver-content
description: The AtaPortReadRegisterUchar routine reads an unsigned byte value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadregisteruchar.htm
old-project: storage
ms.assetid: 1baa8d01-b889-4f2b-ad9e-f35078f7b3d8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortReadRegisterUchar routine [Storage Devices], storage.ataportreadregisteruchar, irb/AtaPortReadRegisterUchar, atartns_63ee26b2-b436-4dc6-a3aa-5a13691e85dd.xml, AtaPortReadRegisterUchar
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
-	AtaPortReadRegisterUchar
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortReadRegisterUchar function


## -description


The <b>AtaPortReadRegisterUchar</b> routine reads an unsigned byte value from the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
UCHAR AtaPortReadRegisterUchar(
  _In_ PUCHAR Register
);
````


## -parameters




### -param Register [in]

A pointer to the register to read. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.


## -returns


<b>AtaPortReadRegisterUchar</b> returns a UCHAR value from the HBA's register. 



## -see-also

<a href="..\irb\nf-irb-ataportreadregisterulong.md">AtaPortReadRegisterUlong</a>

<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>

<a href="..\irb\nf-irb-ataportreadregisterushort.md">AtaPortReadRegisterUshort</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortReadRegisterUchar routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

