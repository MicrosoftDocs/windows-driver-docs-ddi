---
UID: NS:portcls.__unnamed_struct_6
title: PCFILTER_DESCRIPTOR (portcls.h)
description: The PCFILTER_DESCRIPTOR structure describes a miniport driver's implementation of a filter. The structure specifies the filter's pins, nodes, connections, and properties.
old-location: audio\pcfilter_descriptor.htm
tech.root: audio
ms.assetid: 11fd8fc0-98aa-4b06-973c-2b175144da42
ms.date: 05/08/2018
ms.keywords: "*PPCFILTER_DESCRIPTOR, PCFILTER_DESCRIPTOR, PCFILTER_DESCRIPTOR structure [Audio Devices], PPCFILTER_DESCRIPTOR, PPCFILTER_DESCRIPTOR structure pointer [Audio Devices], audio.pcfilter_descriptor, audpc-struct_8413fa35-0c5e-436a-8b0d-b7b08bc73621.xml, portcls/PCFILTER_DESCRIPTOR, portcls/PPCFILTER_DESCRIPTOR"
ms.topic: struct
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Windows
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
- portcls.h
api_name:
- PCFILTER_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: PCFILTER_DESCRIPTOR, *PPCFILTER_DESCRIPTOR
---

# PCFILTER_DESCRIPTOR structure


## -description


The <b>PCFILTER_DESCRIPTOR</b> structure describes a miniport driver's implementation of a filter. The structure specifies the filter's pins, nodes, connections, and properties.


## -struct-fields




### -field Version

Reserved. Initialize to zero.


### -field AutomationTable

Pointer to the automation table. This is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537685">PCAUTOMATION_TABLE</a>. The automation table specifies the handlers for the properties of the filter instance.


### -field PinSize

Specifies the size in bytes of each element in the <b>Pins</b> array. This value should be a multiple of eight and should be at least <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/ff537721">PCPIN_DESCRIPTOR</a>). Larger values allow client-specific descriptor information to be appended to pin descriptors.


### -field PinCount

Specifies the number of pin descriptors in the <b>Pins</b> array.


### -field Pins

Pointer to the array of pin descriptors. Each array element is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537721">PCPIN_DESCRIPTOR</a> structure.


### -field NodeSize

Specifies the size in bytes of each element in the <b>Nodes</b> array. This value should be a multiple of eight and should be at least <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/ff537720">PCNODE_DESCRIPTOR</a>). Larger values allow client-specific descriptor information to be appended to node descriptors.


### -field NodeCount

Specifies the number of node descriptors in the <b>Nodes</b> array.


### -field Nodes

Pointer to the array of node descriptors. Each array element is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537720">PCNODE_DESCRIPTOR</a> structure.


### -field ConnectionCount

Specifies the number of connections in the <b>Connections</b> array.


### -field Connections

Pointer to the array of connections descriptors. Each array element is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537688">PCCONNECTION_DESCRIPTOR</a> structure.


### -field CategoryCount

Specifies the number of GUIDs in the <b>Categories</b> array.


### -field Categories

Pointer to the array of GUIDs that specifies the categories that the object belongs to. See the discussion of topology categories in <a href="https://msdn.microsoft.com/824cc6a2-702a-4e51-91b1-ab776b1babf1">Installing Device Interfaces for an Audio Adapter</a>.


## -remarks



A port driver obtains the miniport driver's filter descriptor by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a> method. The filter descriptor is a <b>PCFILTER_DESCRIPTOR</b> structure describing the miniport driver's pins, nodes, connections, and properties. For more information, see <a href="https://msdn.microsoft.com/e0d52e97-459f-4095-9cf5-1474117ce66a">Filter, Pin, and Node Properties</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537685">PCAUTOMATION_TABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537688">PCCONNECTION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537720">PCNODE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537721">PCPIN_DESCRIPTOR</a>
 

 

