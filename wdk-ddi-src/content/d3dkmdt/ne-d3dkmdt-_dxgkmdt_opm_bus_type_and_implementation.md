---
UID: NE:d3dkmdt._DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION
title: "_DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION"
author: windows-driver-content
description: The DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION enumeration contains values that indicate the type and implementation of the bus that connects a graphics adapter to a motherboard chipset's north bridge.
old-location: display\dxgkmdt_opm_bus_type_and_implementation.htm
old-project: display
ms.assetid: 9023eee6-3832-4da6-8c11-319b048c8ada
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP, DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION, d3dkmdt/DXGKMDT_OPM_BUS_TYPE_AGP, display.dxgkmdt_opm_bus_type_and_implementation, d3dkmdt/DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION, DXGKMDT_OPM_COPP_COMPATIBLE_BUS_TYPE_INTEGRATED, DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR_INSIDE_OF_NUAE, d3dkmdt/DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_NON_STANDARD, d3dkmdt/DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_SOCKET, DXGKMDT_OPM_BUS_TYPE_OTHER, d3dkmdt/DXGKMDT_OPM_COPP_COMPATIBLE_BUS_TYPE_INTEGRATED, DXGKMDT_OPM_BUS_TYPE_PCI, DmEnums_32fcacb0-7c75-4614-8e2d-82fc5ffa68b5.xml, d3dkmdt/DXGKMDT_OPM_BUS_TYPE_OTHER, DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR, DXGKMDT_OPM_BUS_TYPE_AGP, DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_INSIDE_OF_CHIPSET, d3dkmdt/DXGKMDT_OPM_BUS_TYPE_PCIEXPRESS, DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_SOCKET, d3dkmdt/DXGKMDT_OPM_BUS_TYPE_PCI, d3dkmdt/DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_INSIDE_OF_CHIPSET, d3dkmdt/DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR_INSIDE_OF_NUAE, d3dkmdt/DXGKMDT_OPM_BUS_TYPE_PCIX, d3dkmdt/DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP, DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_NON_STANDARD, d3dkmdt/DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR, _DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION, DXGKMDT_OPM_BUS_TYPE_PCIEXPRESS, DXGKMDT_OPM_BUS_TYPE_PCIX, DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION enumeration [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION
---

# _DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION enumeration


## -description


The DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION enumeration contains values that indicate the type and implementation of the bus that connects a graphics adapter to a motherboard chipset's north bridge. These values let an OPM application determine if it must encrypt data when the data is transferred from a computer's main memory to the graphics adapter.


## -syntax


````
typedef enum _DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION { 
  DXGKMDT_OPM_BUS_TYPE_OTHER                                                       = 0x00000000,
  DXGKMDT_OPM_BUS_TYPE_PCI                                                         = 0x00000001,
  DXGKMDT_OPM_BUS_TYPE_PCIX                                                        = 0x00000002,
  DXGKMDT_OPM_BUS_TYPE_PCIEXPRESS                                                  = 0x00000003,
  DXGKMDT_OPM_BUS_TYPE_AGP                                                         = 0x00000004,
  DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_INSIDE_OF_CHIPSET                        = 0x00010000,
  DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP           = 0x00020000,
  DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_SOCKET         = 0x00030000,
  DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR                 = 0x00040000,
  DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR_INSIDE_OF_NUAE  = 0x00050000,
  DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_NON_STANDARD                             = 0x80000000,
  DXGKMDT_OPM_COPP_COMPATIBLE_BUS_TYPE_INTEGRATED                                  = 0x80000000
} DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION;
````


## -enum-fields




#### - DXGKMDT_OPM_BUS_TYPE_OTHER

Indicates that the graphics adapter does not communicate with the north bridge by using the PCI, PCI-X, PCI Express, or AGP expansion bus. 


#### - DXGKMDT_OPM_BUS_TYPE_PCI

Indicates that the PCI bus is used to transfer data from a computer's main memory to the graphics adapter. For information about the PCI bus, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=71290">PCI Local Bus Specification</a>. 


#### - DXGKMDT_OPM_BUS_TYPE_PCIX

Indicates that the PCI-X bus is used to transfer data from a computer's main memory to the graphics adapter. For information about PCI-X, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=71293">PCI-X Specification</a>. 


#### - DXGKMDT_OPM_BUS_TYPE_PCIEXPRESS

Indicates that the PCI Express bus is used to transfer data from a computer's main memory to the graphics adapter. For information about PCI Express, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=69486">PCI Express Specification</a>. 


#### - DXGKMDT_OPM_BUS_TYPE_AGP

Indicates that the Accelerated Graphics Port (AGP) is used to transfer data from a computer's main memory to the graphics adapter. 


#### - DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_INSIDE_OF_CHIPSET

Indicates that the implementation for the graphics adapter is in a motherboard chipset's north bridge. A graphics adapter reports this implementation modifier to imply that data never goes over an expansion bus when data is transferred from main memory to the graphics adapter. PCI, PCI-X, PCI Express, and AGP are examples of expansion buses. This value cannot be combined with DXGKMDT_OPM_BUS_TYPE_PCI, DXGKMDT_OPM_BUS_TYPE_PCIX, DXGKMDT_OPM_BUS_TYPE_PCIEXPRESS, or DXGKMDT_OPM_BUS_TYPE_AGP. This value should only be set if an OPM protected output has OPM semantics. 


#### - DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP

Indicates that the graphics adapter is connected to a motherboard chipset's north bridge by tracks on the motherboard and all of the graphics adapter's chips (integrated circuits (ICs)) are soldered to the motherboard. This value can be combined with any bus-type value (DXGKMDT_OPM_BUS_TYPE_PCI, DXGKMDT_OPM_BUS_TYPE_PCIX, DXGKMDT_OPM_BUS_TYPE_PCIEXPRESS, or DXGKMDT_OPM_BUS_TYPE_AGP) and should only be set if an OPM-protected output has OPM semantics. For more information about this bus-implementation modifier, see the Remarks section. 


#### - DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_SOCKET

Indicates that the graphics adapter is connected to a motherboard chipset's north bridge by tracks on the motherboard and all of the graphics adapter's chips are connected through sockets to the motherboard. This value can be combined with any bus-type value (DXGKMDT_OPM_BUS_TYPE_PCI, DXGKMDT_OPM_BUS_TYPE_PCIX, DXGKMDT_OPM_BUS_TYPE_PCIEXPRESS, or DXGKMDT_OPM_BUS_TYPE_AGP) and should only be set if an OPM-protected output has OPM semantics. For more information about this bus-implementation modifier, see the Remarks section. 


#### - DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR

Indicates that the graphics adapter is connected to the motherboard through a daughterboard connector. Mobile PCI Express Module (MXM) and Advanced eXpress I/O Module (Axiom) are examples of daughterboard connectors. This value should be set only if an OPM-protected output has OPM semantics. 


#### - DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_DAUGHTER_BOARD_CONNECTOR_INSIDE_OF_NUAE

Indicates that the graphics adapter is connected to the motherboard through a daughterboard connector and that the graphics adapter is inside a non-user accessible enclosure (NUAE). This value should be set only if an OPM-protected output has OPM semantics. 


#### - DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_NON_STANDARD

(Optional.) Indicates that any of the optional implementation modifier values (DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_Xxx) are set in the 32-bit bus characteristics ULONG value. For more information about this ULONG, see the Remarks section. This value should be set only if an OPM-protected output has OPM semantics. 


#### - DXGKMDT_OPM_COPP_COMPATIBLE_BUS_TYPE_INTEGRATED

This value can only be set if an OPM-protected output has COPP semantics and should not be set if an OPM-protected output has OPM semantics. This value is equivalent to the <a href="https://msdn.microsoft.com/c9ff0fd3-c063-4450-ae66-54153b3dc53c">COPP</a> COPP_BusType_Integrated flag that is used in the <b>dwData</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppstatusdata.md">DXVA_COPPStatusData</a> structure in the <a href="https://msdn.microsoft.com/24cb232b-e289-45c8-8d55-42614a4dfd54">Windows 2000 Display Driver Model</a>. 


## -remarks


A graphics adapter's display miniport driver should use one bus type (DXGKMDT_OPM_BUS_TYPE_Xxx) and can also use one optional implementation modifier (DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_Xxx). A graphics adapter must report the DXGKMDT_OPM_BUS_TYPE_OTHER value if its bus cannot be described by any other bus-type value or a combination of a bus-type value and an implementation-modifier value.

OPM stores a bus's characteristics in a 32-bit ULONG value. A graphics adapter's display miniport driver uses the bitwise OR operator (|) to combine a bus-type value, an optional implementation-modifier value, and, possibly, the DXGKMDT_OPM_BUS_IMPLEMENTATION_NON_STANDARD flag. The DXGKMDT_OPM_BUS_IMPLEMENTATION_NON_STANDARD value is optional and is set only if an implementation-modifier value is set. This 32-bit ULONG is used when the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) passes the DXGKMDT_OPM_GET_ADAPTER_BUS_TYPE GUID in a call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> or <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> function. The driver sets this 32-bit ULONG in the <b>ulInformation</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_standard_information.md">DXGKMDT_OPM_STANDARD_INFORMATION</a> structure that is retrieved in the <i>DxgkDdiOPMGetInformation</i> or <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> call. For more information about retrieving the graphics adapter's bus type, see the <a href="https://msdn.microsoft.com/20e268b8-fea0-48dd-a3cd-3cbb4233ef99">Retrieving Information about a Protected Output</a> or <a href="https://msdn.microsoft.com/9114f232-4123-47a8-b43d-62d14b9f6b08">Retrieving COPP-Compatible Information about a Protected Output</a> section.

When a bus-type value (for example, DXGKMDT_OPM_BUS_TYPE_PCI) is combined with a bus-implementation modifier value (for example, DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP), the graphics adapter uses most of the PCI specification to communicate with the computer. However, the graphics adapter does not use a physical PCI connector. Basically, the only difference between a regular PCI graphics adapter and an adapter with the DXGKMDT_OPM_BUS_IMPLEMENTATION_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP modifier is that the former is on a card that can be plugged into a PCI slot and the later is directly connected to the motherboard and cannot be removed or upgraded by the user.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_standard_information.md">DXGKMDT_OPM_STANDARD_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

