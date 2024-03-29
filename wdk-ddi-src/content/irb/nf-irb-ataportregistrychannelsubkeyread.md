---
UID: NF:irb.AtaPortRegistryChannelSubkeyRead
title: AtaPortRegistryChannelSubkeyRead function (irb.h)
description: The AtaPortRegistryChannelSubKeyRead routine reads the data that is associated with the indicated value name under the registry key HKLM\CurrentControlSet\Services\<service name>\ControllerN\ChannelM, where N is the number of the controller and M is the number of the channel. Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\ataportregistrychannelsubkeyread.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["AtaPortRegistryChannelSubkeyRead function"]
ms.keywords: AtaPortRegistryChannelSubKeyRead, AtaPortRegistryChannelSubkeyRead, AtaPortRegistryChannelSubkeyRead routine [Storage Devices], atartns_35b220a8-6f27-43c3-90b7-fc0ef628b270.xml, irb/AtaPortRegistryChannelSubkeyRead, storage.ataportregistrychannelsubkeyread
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
targetos: Windows
req.typenames: 
f1_keywords:
 - AtaPortRegistryChannelSubkeyRead
 - irb/AtaPortRegistryChannelSubkeyRead
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - irb.h
api_name:
 - AtaPortRegistryChannelSubkeyRead
---

# AtaPortRegistryChannelSubkeyRead function


## -description

The <b>AtaPortRegistryChannelSubKeyRead</b> routine reads the data that is associated with the indicated value name under the registry key `HKLM\CurrentControlSet\Services\<service name>\ControllerN\ChannelM`, where <i>N </i>is the number of the controller and <i>M </i>is the number of the channel. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

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

<p>A pointer to the number of bytes of data to copy. If the operation fails, the location that is pointed to by <i>Length</i> will update to the length of data that was successfully copied from the registry.</p>

## -returns

<b>AtaPortRegistryChannelSubKeyRead</b> returns <b>TRUE</b> if the operation succeeds. Otherwise, it returns <b>FALSE</b>. The routine also returns <b>FALSE</b> if the miniport driver does not call it from the correct routine.

## -remarks

The buffer that is pointed to by <i>Buffer </i>must be allocated by using <a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportregistryallocatebuffer">AtaPortRegistryAllocateBuffer</a>. 

The miniport driver must call <b>AtaPortRegistryChannelSubKeyRead</b> either during the <a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_channel_init">AtaChannelInitRoutine</a> routine or the <a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_control">IdeHwControl</a> routine or it will return <b>FALSE</b>. Additionally, the miniport driver can only call <b>AtaPortRegistryChannelSubKeyRead</b> from its <b><i>IdeHwControl</i></b> routine if its <b><i>IdeHwControl</i></b> routine was called and had a value of either <b>StartChannel </b>or <b>StopChannel</b> in its <i>ControlAction </i>parameter.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_channel_init">AtaChannelInitRoutine</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportregistryallocatebuffer">AtaPortRegistryAllocateBuffer</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportregistrychannelsubkeywrite">AtaPortRegistryChannelSubKeyWrite</a>



<a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_control">IdeHwControl</a>
