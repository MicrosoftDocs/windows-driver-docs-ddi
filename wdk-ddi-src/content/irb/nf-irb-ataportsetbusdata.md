---
UID: NF:irb.AtaPortSetBusData
title: AtaPortSetBusData function
author: windows-driver-content
description: The AtaPortSetBusData routine stores the data at Buffer in the indicated device's PCI configuration space at an offset that is specified in ConfigDataOffset.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\ataportsetbusdata.htm
old-project: storage
ms.assetid: 5cc65ef9-7447-4775-bf5d-6dadd78f166c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ataportsetbusdata, AtaPortSetBusData, irb/AtaPortSetBusData, atartns_85424997-1f6e-4f48-98f0-e92a7312e62a.xml, AtaPortSetBusData routine [Storage Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Pciidex.lib
-	Pciidex.dll
apiname:
-	AtaPortSetBusData
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortSetBusData function


## -description


The <b>AtaPortSetBusData</b> routine stores the data at <i>Buffer </i>in the indicated device's PCI configuration space at an offset that is specified in <i>ConfigDataOffset</i>.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
ULONG AtaPortSetBusData(
   IN PVOID ControllerExtension,
   IN PVOID Buffer,
   IN PVOID DataMask,
   IN ULONG ConfigDataOffset,
   IN ULONG BufferLength
);
````


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

<a href="..\irb\nf-irb-ataportgetbusdata.md">AtaPortGetBusData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortSetBusData routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

