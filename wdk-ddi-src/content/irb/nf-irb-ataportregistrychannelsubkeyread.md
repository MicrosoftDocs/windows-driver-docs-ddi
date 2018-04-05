---
UID: NF:irb.AtaPortRegistryChannelSubkeyRead
title: AtaPortRegistryChannelSubkeyRead function
author: windows-driver-content
description: The AtaPortRegistryChannelSubKeyRead routine reads the data that is associated with the indicated value name under the registry key HKLM\CurrentControlSet\Services\&lt;service name&gt;\ControllerN\ChannelM, where N is the number of the controller and M is the number of the channel. Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\ataportregistrychannelsubkeyread.htm
old-project: storage
ms.assetid: 50fc7a8c-64ee-4a0c-9106-a071a7cefc34
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortRegistryChannelSubkeyRead, AtaPortRegistryChannelSubkeyRead routine [Storage Devices], atartns_35b220a8-6f27-43c3-90b7-fc0ef628b270.xml, irb/AtaPortRegistryChannelSubkeyRead, storage.ataportregistrychannelsubkeyread
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
-	AtaPortRegistryChannelSubkeyRead
product:
- Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortRegistryChannelSubkeyRead function


## -description


The <b>AtaPortRegistryChannelSubKeyRead</b> routine reads the data that is associated with the indicated value name under the registry key <b>HKLM\CurrentControlSet\Services\</b><i>&lt;service name&gt;</i><b>\Controller</b><i>N</i>\<b>Channel</b><i>M</i>, where <i>N </i>is the number of the controller and <i>M </i>is the number of the channel. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension. 


### -param ControllerNumber [in]

Contains the controller number. 


### -param ValueName [in]

Contains the name of the registry value from which to read. 


### -param ValueType [in]

Indicates the type of data that is contained in the registry value. This member should be assigned one of values indicated in the following table. 

<table>
<tr>
<th>Value</th>
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
A null-terminated. Unicode string. 

</td>
</tr>
</table>
 


### -param Buffer [out, optional]

A pointer to the destination buffer where the data that is read from the registry will be written. 


### -param BufferLength

TBD




#### - Length [in, out]

A pointer to the number of bytes of data to copy. If the operation fails, the location that is pointed to by <i>Length</i> will update to the length of data that was successfully copied from the registry.


## -returns



<b>AtaPortRegistryChannelSubKeyRead</b> returns <b>TRUE</b> if the operation succeeds. Otherwise, it returns <b>FALSE</b>. The routine also returns <b>FALSE</b> if the miniport driver does not call it from the correct routine.




## -remarks



The buffer that is pointed to by <i>Buffer </i>must be allocated by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff550200">AtaPortRegistryAllocateBuffer</a>. 

The miniport driver must call <b>AtaPortRegistryChannelSubKeyRead</b> either during the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550141">AtaChannelInitRoutine</a> routine or the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a> routine or it will return <b>FALSE</b>. Additionally, the miniport driver can only call <b>AtaPortRegistryChannelSubKeyRead</b> from its <b><i>IdeHwControl</i></b> routine if its <b><i>IdeHwControl</i></b> routine was called and had a value of either <b>StartChannel </b>or <b>StopChannel</b> in its <i>ControlAction </i>parameter. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550141">AtaChannelInitRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550200">AtaPortRegistryAllocateBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550204">AtaPortRegistryChannelSubKeyWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a>
 

 

