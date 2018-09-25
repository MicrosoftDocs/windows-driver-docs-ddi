---
UID: NF:irb.AtaPortRegistryControllerKeyRead
title: AtaPortRegistryControllerKeyRead function
author: windows-driver-content
description: The AtaPortRegistryControllerKeyRead routine reads the data that is associated with the indicated value name under the registry key HKLM\CurrentControlSet\Services\&lt;service name&gt;\ControllerN, where N is the number of the controller.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\ataportregistrycontrollerkeyread.htm
tech.root: storage
ms.assetid: 7db22027-49ac-4ee5-8da7-bbd16c97a35b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortRegistryControllerKeyRead, AtaPortRegistryControllerKeyRead routine [Storage Devices], atartns_eea8e60c-8cbd-4632-b5a4-17639f02f4d8.xml, irb/AtaPortRegistryControllerKeyRead, storage.ataportregistrycontrollerkeyread
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	irb.h
api_name:
-	AtaPortRegistryControllerKeyRead
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortRegistryControllerKeyRead function


## -description


The <b>AtaPortRegistryControllerKeyRead</b> routine reads the data that is associated with the indicated value name under the registry key <b>HKLM\CurrentControlSet\Services\</b><i>&lt;service name&gt;</i><b>\Controller</b><i>N</i>, where <i>N </i>is the number of the controller.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension. 


### -param ControllerNumber [in]

Contains the controller number. 


### -param ValueName [in]

Contains the name of the registry value to read. 


### -param ValueType [in]

Indicates the type of the data that is contained in the registry value. This parameter should be assigned one of values indicated in the following table.

<table>
<tr>
<th>Value type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
IDE_REG_DWORD

</td>
<td>
A 4-byte numeric value. 

</td>
</tr>
<tr>
<td>
IDE_REG_BINARY

</td>
<td>
Binary data. 

</td>
</tr>
<tr>
<td>
IDE_REG_SZ

</td>
<td>
A null-terminated, Unicode string. 

</td>
</tr>
</table>
 


### -param Buffer [out, optional]

A pointer to the buffer where the results are to be copied. 


### -param BufferLength

<p>A pointer to the number of bytes of data to copy. If the operation fails because of an insufficient buffer, the location that is pointed to by <i>Length</i> will update to the actual length of the data in the registry.</p>




## -returns



<b>AtaPortRegistryControllerKeyRead</b> returns <b>TRUE</b> if the operation succeeds. Otherwise, it returns <b>FALSE</b>. The <b>AtaPortRegistryControllerKeyRead</b> routine also returns <b>FALSE</b> if the miniport driver does not call it from the correct routine.




## -remarks



The buffer at <i>Buffer</i> must be allocated by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff550200">AtaPortRegistryAllocateBuffer</a>. 

The miniport driver must call <b>AtaPortRegistryControllerKeyRead</b> either in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff550141">AtaChannelInitRoutine</a> routine or in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a> routine. It cannot call <b>AtaPortRegistryControllerKeyRead</b> from any other routine. Additionally, the miniport driver can only call <b>AtaPortRegistryControllerKeyRead</b> from its <b>IdeHwControl</b> routine if its <b>IdeHwControl</b> routine was called and had a value of either <b>StartChannel</b> or <b>StopChannel</b> in its <i>ControlAction </i>parameter. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550141">AtaChannelInitRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550200">AtaPortRegistryAllocateBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a>
 

 

