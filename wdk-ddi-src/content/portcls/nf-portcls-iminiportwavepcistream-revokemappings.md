---
UID: NF:portcls.IMiniportWavePciStream.RevokeMappings
title: IMiniportWavePciStream::RevokeMappings (portcls.h)
description: The RevokeMappings method revokes mappings that were previously obtained through IPortWavePciStream::GetMapping.
old-location: audio\iminiportwavepcistream_revokemappings.htm
tech.root: audio
ms.assetid: a6534917-5fe6-449b-8e85-398d26730f66
ms.date: 05/08/2018
keywords: ["IMiniportWavePciStream::RevokeMappings"]
ms.keywords: IMiniportWavePciStream interface [Audio Devices],RevokeMappings method, IMiniportWavePciStream.RevokeMappings, IMiniportWavePciStream::RevokeMappings, RevokeMappings, RevokeMappings method [Audio Devices], RevokeMappings method [Audio Devices],IMiniportWavePciStream interface, audio.iminiportwavepcistream_revokemappings, audmp-routines_f995bc15-917a-416d-9066-3d5667866973.xml, portcls/IMiniportWavePciStream::RevokeMappings
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IMiniportWavePciStream::RevokeMappings
 - portcls/IMiniportWavePciStream::RevokeMappings
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWavePciStream.RevokeMappings
---

# IMiniportWavePciStream::RevokeMappings


## -description

The <code>RevokeMappings</code> method revokes mappings that were previously obtained through <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavepcistream-getmapping">IPortWavePciStream::GetMapping</a>.

## -parameters

### -param FirstTag 

[in]
Specifies the tag value that identifies the first mapping that is being revoked.

### -param LastTag 

[in]
Specifies the tag value that identifies the last mapping that is being revoked.

### -param MappingsRevoked 

[out]
Output pointer for the count of revoked mappings. This parameter points to a ULONG variable into which the method writes the number of mappings actually revoked by the call. This number excludes any mappings in the range <i>FirstTag</i> to <i>LastTag</i> that the miniport driver has already released. Due to synchronization issues, some of the mappings in the range might be released between the time that the port driver determines the list of mappings to be revoked and the call to <code>RevokeMappings</code>. For more information, see the following Remarks section.

## -returns

<code>RevokeMappings</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

The port driver calls <code>RevokeMappings</code> to revoke the stream's mappings when:

<ul>
<li>
An I/O request (IRP) is canceled and the previously mapped memory might no longer be available.

</li>
<li>
The stream state changes to KSSTATE_STOP (see <a href="/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a>) and the device no longer has need for the mappings.

</li>
</ul>
The miniport driver keeps track of the order in which it acquires its mappings from calls to <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavepcistream-getmapping">IPortWavePciStream::GetMapping</a>. The <code>RevokeMapping</code> method revokes all mappings in the sequence that begins with the mapping identified by <i>FirstTag</i> and ends with the mapping identified by <i>LastTag</i>. This includes the mappings identified by <i>FirstTag</i> and <i>LastTag</i> and all mappings in between. The miniport driver revokes each mapping by removing it from the list of available mappings.

The <code>RevokeMapping</code> method can be used to remove a single mapping by setting <i>FirstTag</i> and <i>LastTag</i> to the same value.

The port driver can call <code>RevokeMappings</code> asynchronously with respect to the miniport driver's maintenance operations on the DMA controller's scatter/gather transfer queue. Access to this queue needs to be protected by a synchronization primitive. For example, in the ac97 sample audio driver in the Microsoft Windows Driver Kit (WDK), this is done by surrounding critical code sections with <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a> and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kereleasespinlock">KeReleaseSpinLock</a> calls. Because the miniport driver can release mappings asynchronously with respect to the port driver's calls to <code>RevokeMappings</code>, the miniport driver might have previously released (see <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavepcistream-releasemapping">IPortWavePciStream::ReleaseMapping</a>) one or more of the mappings specified in the <code>RevokeMappings</code> call.

For more information about mappings, see <a href="/windows-hardware/drivers/audio/wavepci-latency">WavePci Latency</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavepcistream">IMiniportWavePciStream</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavepcistream-getmapping">IPortWavePciStream::GetMapping</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavepcistream-releasemapping">IPortWavePciStream::ReleaseMapping</a>



<a href="/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kereleasespinlock">KeReleaseSpinLock</a>