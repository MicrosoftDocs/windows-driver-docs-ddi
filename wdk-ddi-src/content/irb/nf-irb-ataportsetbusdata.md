---
UID: NF:irb.AtaPortSetBusData
title: AtaPortSetBusData function
author: windows-driver-content
description: The AtaPortSetBusData routine stores the data at Buffer in the indicated device's PCI configuration space at an offset that is specified in ConfigDataOffset.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\ataportsetbusdata.htm
old-project: storage
ms.assetid: 5cc65ef9-7447-4775-bf5d-6dadd78f166c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortSetBusData, AtaPortSetBusData routine [Storage Devices], atartns_85424997-1f6e-4f48-98f0-e92a7312e62a.xml, irb/AtaPortSetBusData, storage.ataportsetbusdata
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
req.lib: Pciidex.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Pciidex.lib
-	Pciidex.dll
api_name:
-	AtaPortSetBusData
product: Windows
targetos: Windows
req.typenames: 
---

# AtaPortSetBusData function


## -description


The <b>AtaPortSetBusData</b> routine stores the data at <i>Buffer </i>in the indicated device's PCI configuration space at an offset that is specified in <i>ConfigDataOffset</i>.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ControllerExtension

A pointer to the controller extension.


### -param Buffer

A pointer to the buffer that contains the data to write to the device's PCI bus configuration space.


### -param ConfigDataOffset

Specifies an offset into the device's PCI bus configuration data space where the data is updated.


### -param BufferLength

Specifies the length, in bytes, of the buffer.


#### - DataMask

Contains a data mask buffer that controls which bits of PCI bus configuration data must be updated. The length of <i>Datamask </i>must be the same length as <i>Buffer.</i>


## -returns



<b>AtaPortSetBusData</b> returns the amount of the data that was written in bytes.




## -remarks



<b>AtaPortSetBusData</b> completes a bitwise OR, one byte at a time, of the current PCI configuration space data with the new data in <i>Buffer</i>. Only those bits not indicated by <i>DataMask</i> are left untouched. The byte of data that follows <i>ConfigDataOffset</i>, therefore, is updated as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ConfigDataOffest[i] = 
    (ConfigDataOffest[i] &amp; ~DataMask[i]) | 
    (DataMask[i] &amp; Buffer[i])</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550158">AtaPortGetBusData</a>
 

 

