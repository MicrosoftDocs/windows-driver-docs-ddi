---
UID: NE:d3dkmdt._DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION
title: _DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION (d3dkmdt.h)
description: The DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION enumeration contains values that indicate the type and implementation of the bus that connects a graphics adapter to a motherboard chipset's north bridge.
old-location: display\dxgkmdt_opm_bus_type_and_implementation.htm
tech.root: display
ms.assetid: 9023eee6-3832-4da6-8c11-319b048c8ada
ms.date: 05/10/2018
keywords: ["_DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION enumeration"]
ms.keywords: DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR, DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR_INSIDE_OF_NUAE, DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_INSIDE_OF_CHIPSET, DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_NON_STANDARD, DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP, DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_SOCKET, DXGKMDT_OPM_BUS_TYPE_AGP, DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION, DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION enumeration [Display Devices], DXGKMDT_OPM_BUS_TYPE_OTHER, DXGKMDT_OPM_BUS_TYPE_PCI, DXGKMDT_OPM_BUS_TYPE_PCIEXPRESS, DXGKMDT_OPM_BUS_TYPE_PCIX, DXGKMDT_OPM_COPP_COMPATIBLE_BUS_TYPE_INTEGRATED, DmEnums_32fcacb0-7c75-4614-8e2d-82fc5ffa68b5.xml, _DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION, d3dkmdt/DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR, d3dkmdt/DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR_INSIDE_OF_NUAE, d3dkmdt/DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_INSIDE_OF_CHIPSET, d3dkmdt/DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_NON_STANDARD, d3dkmdt/DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP, d3dkmdt/DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_SOCKET, d3dkmdt/DXGKMDT_OPM_BUS_TYPE_AGP, d3dkmdt/DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION, d3dkmdt/DXGKMDT_OPM_BUS_TYPE_OTHER, d3dkmdt/DXGKMDT_OPM_BUS_TYPE_PCI, d3dkmdt/DXGKMDT_OPM_BUS_TYPE_PCIEXPRESS, d3dkmdt/DXGKMDT_OPM_BUS_TYPE_PCIX, d3dkmdt/DXGKMDT_OPM_COPP_COMPATIBLE_BUS_TYPE_INTEGRATED, display.dxgkmdt_opm_bus_type_and_implementation
f1_keywords:
 - "d3dkmdt/DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION"
 - "DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION"
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- d3dkmdt.h
api_name:
- DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION
targetos: Windows
req.typenames: DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION
---

# _DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION enumeration


## -description


The DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION enumeration contains values that indicate the type and implementation of the bus that connects a graphics adapter to a motherboard chipset's north bridge. These values let an OPM application determine if it must encrypt data when the data is transferred from a computer's main memory to the graphics adapter.


## -enum-fields




### -field DXGKMDT_OPM_BUS_TYPE_OTHER

Indicates that the graphics adapter does not communicate with the north bridge by using the PCI, PCI-X, PCI Express, or AGP expansion bus. 


### -field DXGKMDT_OPM_BUS_TYPE_PCI

Indicates that the PCI bus is used to transfer data from a computer's main memory to the graphics adapter. For information about the PCI bus, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=71290">PCI Local Bus Specification</a>. 


### -field DXGKMDT_OPM_BUS_TYPE_PCIX

Indicates that the PCI-X bus is used to transfer data from a computer's main memory to the graphics adapter. For information about PCI-X, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=71293">PCI-X Specification</a>. 


### -field DXGKMDT_OPM_BUS_TYPE_PCIEXPRESS

Indicates that the PCI Express bus is used to transfer data from a computer's main memory to the graphics adapter. For information about PCI Express, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=69486">PCI Express Specification</a>. 


### -field DXGKMDT_OPM_BUS_TYPE_AGP

Indicates that the Accelerated Graphics Port (AGP) is used to transfer data from a computer's main memory to the graphics adapter. 


### -field DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_INSIDE_OF_CHIPSET

Indicates that the implementation for the graphics adapter is in a motherboard chipset's north bridge. A graphics adapter reports this implementation modifier to imply that data never goes over an expansion bus when data is transferred from main memory to the graphics adapter. PCI, PCI-X, PCI Express, and AGP are examples of expansion buses. This value cannot be combined with DXGKMDT_OPM_BUS_TYPE_PCI, DXGKMDT_OPM_BUS_TYPE_PCIX, DXGKMDT_OPM_BUS_TYPE_PCIEXPRESS, or DXGKMDT_OPM_BUS_TYPE_AGP. This value should only be set if an OPM protected output has OPM semantics. 


### -field DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP

Indicates that the graphics adapter is connected to a motherboard chipset's north bridge by tracks on the motherboard and all of the graphics adapter's chips (integrated circuits (ICs)) are soldered to the motherboard. This value can be combined with any bus-type value (DXGKMDT_OPM_BUS_TYPE_PCI, DXGKMDT_OPM_BUS_TYPE_PCIX, DXGKMDT_OPM_BUS_TYPE_PCIEXPRESS, or DXGKMDT_OPM_BUS_TYPE_AGP) and should only be set if an OPM-protected output has OPM semantics. For more information about this bus-implementation modifier, see the Remarks section. 


### -field DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_SOCKET

Indicates that the graphics adapter is connected to a motherboard chipset's north bridge by tracks on the motherboard and all of the graphics adapter's chips are connected through sockets to the motherboard. This value can be combined with any bus-type value (DXGKMDT_OPM_BUS_TYPE_PCI, DXGKMDT_OPM_BUS_TYPE_PCIX, DXGKMDT_OPM_BUS_TYPE_PCIEXPRESS, or DXGKMDT_OPM_BUS_TYPE_AGP) and should only be set if an OPM-protected output has OPM semantics. For more information about this bus-implementation modifier, see the Remarks section. 


### -field DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR

Indicates that the graphics adapter is connected to the motherboard through a daughterboard connector. Mobile PCI Express Module (MXM) and Advanced eXpress I/O Module (Axiom) are examples of daughterboard connectors. This value should be set only if an OPM-protected output has OPM semantics. 


### -field DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR_INSIDE_OF_NUAE

Indicates that the graphics adapter is connected to the motherboard through a daughterboard connector and that the graphics adapter is inside a non-user accessible enclosure (NUAE). This value should be set only if an OPM-protected output has OPM semantics. 


### -field DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_NON_STANDARD

(Optional.) Indicates that any of the optional implementation modifier values (DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_Xxx) are set in the 32-bit bus characteristics ULONG value. For more information about this ULONG, see the Remarks section. This value should be set only if an OPM-protected output has OPM semantics. 


### -field DXGKMDT_OPM_COPP_COMPATIBLE_BUS_TYPE_INTEGRATED

This value can only be set if an OPM-protected output has COPP semantics and should not be set if an OPM-protected output has OPM semantics. This value is equivalent to the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/copp-processing">COPP</a> COPP_BusType_Integrated flag that is used in the <b>dwData</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppstatusdata">DXVA_COPPStatusData</a> structure in the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/windows-2000-display-driver-model-design-guide">Windows 2000 Display Driver Model</a>. 


## -remarks



A graphics adapter's display miniport driver should use one bus type (DXGKMDT_OPM_BUS_TYPE_Xxx) and can also use one optional implementation modifier (DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_Xxx). A graphics adapter must report the DXGKMDT_OPM_BUS_TYPE_OTHER value if its bus cannot be described by any other bus-type value or a combination of a bus-type value and an implementation-modifier value.

OPM stores a bus's characteristics in a 32-bit ULONG value. A graphics adapter's display miniport driver uses the bitwise OR operator (|) to combine a bus-type value, an optional implementation-modifier value, and, possibly, the DXGKMDT_OPM_BUS_IMPLEMENTATION_NON_STANDARD flag. The DXGKMDT_OPM_BUS_IMPLEMENTATION_NON_STANDARD value is optional and is set only if an implementation-modifier value is set. This 32-bit ULONG is used when the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) passes the DXGKMDT_OPM_GET_ADAPTER_BUS_TYPE GUID in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information">DxgkDdiOPMGetCOPPCompatibleInformation</a> function. The driver sets this 32-bit ULONG in the <b>ulInformation</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_standard_information">DXGKMDT_OPM_STANDARD_INFORMATION</a> structure that is retrieved in the <i>DxgkDdiOPMGetInformation</i> or <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> call. For more information about retrieving the graphics adapter's bus type, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/retrieving-information-about-a-protected-output">Retrieving Information about a Protected Output</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/display/retrieving-copp-compatible-information-about-a-protected-output">Retrieving COPP-Compatible Information about a Protected Output</a> section.

When a bus-type value (for example, DXGKMDT_OPM_BUS_TYPE_PCI) is combined with a bus-implementation modifier value (for example, DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP), the graphics adapter uses most of the PCI specification to communicate with the computer. However, the graphics adapter does not use a physical PCI connector. Basically, the only difference between a regular PCI graphics adapter and an adapter with the DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP modifier is that the former is on a card that can be plugged into a PCI slot and the later is directly connected to the motherboard and cannot be removed or upgraded by the user.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_standard_information">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a>
 

 

