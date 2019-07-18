---
UID: NF:portcls.PcNewPort
title: PcNewPort function (portcls.h)
description: The PcNewPort function creates a new system-supplied port-driver object, whose interface (derived from base class IPort) is specified by a class ID.
old-location: audio\pcnewport.htm
tech.root: audio
ms.assetid: d948b69c-c5cd-4614-a646-76acb493e8de
ms.date: 05/08/2018
ms.keywords: PcNewPort, PcNewPort function [Audio Devices], audio.pcnewport, audpc-routines_799c0416-dde0-4818-8da7-a38e4e6d4541.xml, portcls/PcNewPort
ms.topic: function
f1_keywords:
 - "portcls/PcNewPort"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Portcls.lib
- Portcls.dll
api_name:
- PcNewPort
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcNewPort function


## -description


The <b>PcNewPort</b> function creates a new system-supplied port-driver object, whose interface (derived from base class <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iport">IPort</a>) is specified by a class ID.


## -parameters




### -param OutPort [out]

Output pointer for the port-driver object created by this function. This parameter points to a caller-allocated pointer variable into which the function outputs the pointer to the newly created <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iport">IPort</a> object. This object has the port interface that is specified by the <i>ClassId</i> parameter. Specify a valid, non-NULL pointer value for this parameter.


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nn-dmusicks-iportdmus">IPortDMus</a>


</td>
</tr>
<tr>
<td>
<b>CLSID_PortMidi</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iportmidi">IPortMidi</a>


</td>
</tr>
<tr>
<td>
<b>CLSID_PortTopology</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iporttopology">IPortTopology</a>


</td>
</tr>
<tr>
<td>
<b>CLSID_PortWaveCyclic</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iportwavecyclic">IPortWaveCyclic</a>


</td>
</tr>
<tr>
<td>
<b>CLSID_PortWavePci</b>

</td>
<td>

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff536905(v=vs.85)">IPortWavePci</a>


</td>
</tr>
<tr>
<td>
<b>CLSID_PortWaveRT</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iportwavert">IPortWaveRT</a>


</td>
</tr>
</table>
 

<b>CLSID_PortDMus</b> is defined in header file dmusicks.h. The other four GUIDs in the preceding table are defined in portcls.h.

In Microsoft Windows XP and later, the MIDI and DirectMusic port drivers share the same internal software implementation. This means that the <b>CLSID_PortMidi</b> GUID is equivalent to <b>CLSID_PortDMus</b>.

For more information about creating port and miniport drivers for subdevices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/subdevice-creation">Subdevice Creation</a>.

The <i>OutPort</i> parameter follows the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iport">IPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nn-dmusicks-iportdmus">IPortDMus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iportmidi">IPortMidi</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iporttopology">IPortTopology</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iportwavecyclic">IPortWaveCyclic</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff536905(v=vs.85)">IPortWavePci</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iportwavert">IPortWaveRT</a>
 

 

