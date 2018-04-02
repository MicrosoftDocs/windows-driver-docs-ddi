---
UID: NE:ntddk._WHEA_ERROR_TYPE
title: "_WHEA_ERROR_TYPE"
author: windows-driver-content
description: The WHEA_ERROR_TYPE enumeration defines the different types of hardware components that can report a hardware error.
old-location: whea\whea_error_type.htm
old-project: whea
ms.assetid: b10dbb47-394c-42f0-9471-6e5deb73a7b9
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_ERROR_TYPE, PWHEA_ERROR_TYPE, PWHEA_ERROR_TYPE enumeration pointer [WHEA Drivers and Applications], WHEA_ERROR_TYPE, WHEA_ERROR_TYPE enumeration [WHEA Drivers and Applications], WheaErrTypeGeneric, WheaErrTypeMemory, WheaErrTypeNMI, WheaErrTypePCIExpress, WheaErrTypePCIXBus, WheaErrTypePCIXDevice, WheaErrTypeProcessor, _WHEA_ERROR_TYPE, ntddk/PWHEA_ERROR_TYPE, ntddk/WHEA_ERROR_TYPE, ntddk/WheaErrTypeGeneric, ntddk/WheaErrTypeMemory, ntddk/WheaErrTypeNMI, ntddk/WheaErrTypePCIExpress, ntddk/WheaErrTypePCIXBus, ntddk/WheaErrTypePCIXDevice, ntddk/WheaErrTypeProcessor, whea.whea_error_type, whearef_4e585fa6-81e5-4196-b7fa-6194d3701835.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_ERROR_TYPE
product: Windows
targetos: Windows
req.typenames: WHEA_ERROR_TYPE, *PWHEA_ERROR_TYPE
---

# _WHEA_ERROR_TYPE enumeration


## -description


The WHEA_ERROR_TYPE enumeration defines the different types of hardware components that can report a hardware error.


## -enum-fields




### -field WheaErrTypeProcessor

A processor reported the hardware error.


### -field WheaErrTypeMemory

The memory hierarchy reported the hardware error.


### -field WheaErrTypePCIExpress

A PCI Express root port reported the hardware error.


### -field WheaErrTypeNMI

A nonmaskable interrupt (NMI) was signaled.


### -field WheaErrTypePCIXBus

A PCI or PCI-X bus reported the hardware error.


### -field WheaErrTypePCIXDevice

A PCI or PCI-X device reported the hardware error.


### -field WheaErrTypeGeneric

A hardware component that does not conform to any of the other WHEA_ERROR_TYPE enumeration values reported the hardware error.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a> structure contains a member of type WHEA_ERROR_TYPE that specifies the type of hardware component that reported the hardware error.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>
 

 

