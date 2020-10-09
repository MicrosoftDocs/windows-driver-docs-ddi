---
UID: NF:portcls.PcNewInterruptSync
title: PcNewInterruptSync function (portcls.h)
description: The PcNewInterruptSync function creates and initializes an interrupt-synchronization object.
old-location: audio\pcnewinterruptsync.htm
tech.root: audio
ms.assetid: 2455d09a-608e-4529-9c27-ed760c7da675
ms.date: 05/08/2018
keywords: ["PcNewInterruptSync function"]
ms.keywords: PcNewInterruptSync, PcNewInterruptSync function [Audio Devices], audio.pcnewinterruptsync, audpc-routines_97a60c6f-2dc1-48db-982a-996b5ab8d741.xml, portcls/PcNewInterruptSync
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available starting in  Windows 2000.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PcNewInterruptSync
 - portcls/PcNewInterruptSync
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Portcls.lib
 - Portcls.dll
api_name:
 - PcNewInterruptSync
---

# PcNewInterruptSync function


## -description

The <b>PcNewInterruptSync</b> function creates and initializes an interrupt-synchronization object.

## -parameters

### -param OutInterruptSync 

[out]
Output pointer for the interrupt-synchronization object created by this function. This parameter points to a caller-allocated pointer variable into which the function outputs a reference to the newly created <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iinterruptsync">IInterruptSync</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.

### -param OuterUnknown 

[in, optional]
Pointer to the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface of an object that needs to aggregate the object. Unless aggregation is required, set this parameter to <b>NULL</b>.

### -param ResourceList 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a> object that was provided to the miniport driver during initialization. The port driver will examine this resource list but will not modify it.

### -param ResourceIndex 

[in]
Specifies the index of the interrupt resource in the resource list. If the <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iresourcelist-numberofentriesoftype">IResourceList::NumberOfEntriesOfType</a> method returns a count of N for type CmResourceTypeInterrupt, <i>ResourceIndex</i> must be a value in the range 0 to N-1.

### -param Mode 

[in]
Specifies the way that multiple ISRs are handled. Set this parameter to one of the INTERRUPTSYNCMODE enumeration values. For more information, see the following Remarks section.

## -returns

<b>PcNewInterruptSync</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

The <i>Mode</i> parameter is set to one of the INTERRUPTSYNCMODE enumeration values in the following table.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>InterruptSyncModeNormal</b>

</td>
<td>
Call each ISR in the list until one of them returns STATUS_SUCCESS.

</td>
</tr>
<tr>
<td>
<b>InterruptSyncModeAll</b>

</td>
<td>
Call each ISR in the list exactly once, regardless of the return codes of the various ISRs.

</td>
</tr>
<tr>
<td>
<b>InterruptSyncModeRepeat</b>

</td>
<td>
Traverse the entire ISR list until a trip through the list occurs in which no ISR in the list returns STATUS_SUCCESS.

</td>
</tr>
</table>
 

For detailed descriptions of these three modes, see <a href="/windows-hardware/drivers/audio/interrupt-sync-objects">Interrupt Sync Objects</a>.

The <i>OutInterruptSync</i>, <i>OuterUnknown</i>, and <i>ResourceList</i> parameters follow the <a href="/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iinterruptsync">IInterruptSync</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iresourcelist-numberofentriesoftype">IResourceList::NumberOfEntriesOfType</a>