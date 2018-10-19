---
UID: NF:portcls.PcNewInterruptSync
title: PcNewInterruptSync function
author: windows-driver-content
description: The PcNewInterruptSync function creates and initializes an interrupt-synchronization object.
old-location: audio\pcnewinterruptsync.htm
tech.root: audio
ms.assetid: 2455d09a-608e-4529-9c27-ed760c7da675
ms.date: 05/08/2018
ms.keywords: PcNewInterruptSync, PcNewInterruptSync function [Audio Devices], audio.pcnewinterruptsync, audpc-routines_97a60c6f-2dc1-48db-982a-996b5ab8d741.xml, portcls/PcNewInterruptSync
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcNewInterruptSync
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcNewInterruptSync function


## -description


The <b>PcNewInterruptSync</b> function creates and initializes an interrupt-synchronization object.


## -parameters




### -param OutInterruptSync [out]

Output pointer for the interrupt-synchronization object created by this function. This parameter points to a caller-allocated pointer variable into which the function outputs a reference to the newly created <a href="https://msdn.microsoft.com/library/windows/hardware/ff536590">IInterruptSync</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in, optional]

Pointer to the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface of an object that needs to aggregate the object. Unless aggregation is required, set this parameter to <b>NULL</b>.


### -param ResourceList [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a> object that was provided to the miniport driver during initialization. The port driver will examine this resource list but will not modify it.


### -param ResourceIndex [in]

Specifies the index of the interrupt resource in the resource list. If the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536988">IResourceList::NumberOfEntriesOfType</a> method returns a count of N for type CmResourceTypeInterrupt, <i>ResourceIndex</i> must be a value in the range 0 to N-1.


### -param Mode [in]

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
 

For detailed descriptions of these three modes, see <a href="https://msdn.microsoft.com/c9e228e0-6178-442d-a82a-6b14ed67c9d2">Interrupt Sync Objects</a>.

The <i>OutInterruptSync</i>, <i>OuterUnknown</i>, and <i>ResourceList</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536590">IInterruptSync</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536988">IResourceList::NumberOfEntriesOfType</a>
 

 

