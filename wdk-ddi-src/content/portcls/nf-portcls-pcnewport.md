---
UID: NF:portcls.PcNewPort
title: PcNewPort function
author: windows-driver-content
description: The PcNewPort function creates a new system-supplied port-driver object, whose interface (derived from base class IPort) is specified by a class ID.
old-location: audio\pcnewport.htm
old-project: audio
ms.assetid: d948b69c-c5cd-4614-a646-76acb493e8de
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: PcNewPort, PcNewPort function [Audio Devices], audio.pcnewport, audpc-routines_799c0416-dde0-4818-8da7-a38e4e6d4541.xml, portcls/PcNewPort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcNewPort function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
-	PcNewPort
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcNewPort function


## -description


The <b>PcNewPort</b> function creates a new system-supplied port-driver object, whose interface (derived from base class <a href="https://msdn.microsoft.com/library/windows/hardware/ff536842">IPort</a>) is specified by a class ID.


## -parameters




### -param OutPort [out]

Output pointer for the port-driver object created by this function. This parameter points to a caller-allocated pointer variable into which the function outputs the pointer to the newly created <a href="https://msdn.microsoft.com/library/windows/hardware/ff536842">IPort</a> object. This object has the port interface that is specified by the <i>ClassId</i> parameter. Specify a valid, non-NULL pointer value for this parameter.


### -param ClassID [in]

Specifies the type of port interface that is being requested. For more information, see the following Remarks section.


## -returns



<b>PcNewPort</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



The <i>ClassId</i> parameter can be set to one of the GUIDs in the following table.

<table>
<tr>
<th>Class GUID</th>
<th>Port Interface Name</th>
</tr>
<tr>
<td>
<b>CLSID_PortDMus</b>

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536879">IPortDMus</a>


</td>
</tr>
<tr>
<td>
<b>CLSID_PortMidi</b>

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536891">IPortMidi</a>


</td>
</tr>
<tr>
<td>
<b>CLSID_PortTopology</b>

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536896">IPortTopology</a>


</td>
</tr>
<tr>
<td>
<b>CLSID_PortWaveCyclic</b>

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536899">IPortWaveCyclic</a>


</td>
</tr>
<tr>
<td>
<b>CLSID_PortWavePci</b>

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536905">IPortWavePci</a>


</td>
</tr>
<tr>
<td>
<b>CLSID_PortWaveRT</b>

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536920">IPortWaveRT</a>


</td>
</tr>
</table>
 

<b>CLSID_PortDMus</b> is defined in header file dmusicks.h. The other four GUIDs in the preceding table are defined in portcls.h.

In Microsoft Windows XP and later, the MIDI and DirectMusic port drivers share the same internal software implementation. This means that the <b>CLSID_PortMidi</b> GUID is equivalent to <b>CLSID_PortDMus</b>.

For more information about creating port and miniport drivers for subdevices, see <a href="https://msdn.microsoft.com/e4ba1209-adc6-48c3-9633-247e9e3849bc">Subdevice Creation</a>.

The <i>OutPort</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536842">IPort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536879">IPortDMus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536891">IPortMidi</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536896">IPortTopology</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536899">IPortWaveCyclic</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536905">IPortWavePci</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536920">IPortWaveRT</a>
 

 

