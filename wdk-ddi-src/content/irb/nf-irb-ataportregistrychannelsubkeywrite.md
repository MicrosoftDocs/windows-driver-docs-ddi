---
UID: NF:irb.AtaPortRegistryChannelSubkeyWrite
title: AtaPortRegistryChannelSubkeyWrite function (irb.h)
description: The AtaPortRegistryChannelSubKeyWrite routine writes data to the indicated value name under the registry key HKLM\CurrentControlSet\Services\<service name>\ControllerN\ChannelM, where N is the number of the controller and M is the number of the channel.
old-location: storage\ataportregistrychannelsubkeywrite.htm
tech.root: storage
ms.assetid: 4072f369-992e-4144-b3b9-1e05bb2127f2
ms.date: 03/29/2018
keywords: ["AtaPortRegistryChannelSubkeyWrite function"]
ms.keywords: AtaPortRegistryChannelSubKeyWrite, AtaPortRegistryChannelSubkeyWrite, AtaPortRegistryChannelSubkeyWrite routine [Storage Devices], atartns_0281129c-7789-44f3-b26d-d3725e7ff165.xml, irb/AtaPortRegistryChannelSubkeyWrite, storage.ataportregistrychannelsubkeywrite
f1_keywords:
 - "irb/AtaPortRegistryChannelSubkeyWrite"
 - "AtaPortRegistryChannelSubkeyWrite"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- irb.h
api_name:
- AtaPortRegistryChannelSubkeyWrite
targetos: Windows
req.typenames: 
---

# AtaPortRegistryChannelSubkeyWrite function


## -description


The <b>AtaPortRegistryChannelSubKeyWrite</b> routine writes data to the indicated value name under the registry key `HKLM\CurrentControlSet\Services\<service name>\ControllerN\ChannelM`, where <i>N </i>is the number of the controller and <i>M </i>is the number of the channel. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension 
[in]
A pointer to the channel extension. 


### -param ControllerNumber 
[in]
Contains the controller number. 


### -param ValueName 
[in]
Contains the name of the registry value to write to. 


### -param ValueType 
[in]
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
A null-terminated, Unicode string. 

</td>
</tr>
</table>
 


### -param Buffer 
[in]
A pointer to the source buffer that contains the data to be written to the registry. 


### -param BufferLength

<p>A pointer to the number of bytes of data to copy. If the operation fails, the location that is pointed to by <i>Length</i> will update to the length of data that was successfully written to the registry.</p>




## -returns



<b>AtaPortRegistryChannelSubKeyWrite</b> returns <b>TRUE</b> if the operation succeeds. Otherwise, it returns <b>FALSE</b>. The routine also returns <b>FALSE</b> if the miniport driver does not call it from the correct routine.




## -remarks



If the value name is not present, <b>AtaPortRegistryChannelSubKeyWrite</b> creates an entry for the value and the data is stored in the newly created value.

The buffer that is pointed to by <i>Buffer </i>must be allocated by using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportregistryallocatebuffer">AtaPortRegistryAllocateBuffer</a>. 

The miniport driver must call <b>AtaPortRegistryChannelSubKeyWrite</b> either during the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_channel_init">AtaChannelInitRoutine</a> routine or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_control">IdeHwControl</a> routine The miniport driver cannot call <b>AtaPortRegistryChannelSubKeyWrite</b> from any other routine without returning <b>FALSE</b>. Additionally, the miniport driver can only call <b>AtaPortRegistryChannelSubKeyWrite</b> from its <b><i>IdeHwControl</i></b> routine if its <b><i>IdeHwControl</i></b> routine was called and had a value of either <b>StartChannel</b> or <b>StopChannel</b> in its <i>ControlAction </i>parameter. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_channel_init">AtaChannelInitRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportregistrychannelsubkeyread">AtaPortRegistryChannelSubKeyRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportregistrychannelsubkeywritedeferred">AtaPortRegistryChannelSubKeyWriteDeferred</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_control">IdeHwControl</a>
 

 

