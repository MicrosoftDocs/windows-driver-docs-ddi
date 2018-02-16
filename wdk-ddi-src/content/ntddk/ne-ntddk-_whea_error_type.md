---
UID: NE:ntddk._WHEA_ERROR_TYPE
title: "_WHEA_ERROR_TYPE"
author: windows-driver-content
description: The WHEA_ERROR_TYPE enumeration defines the different types of hardware components that can report a hardware error.
old-location: whea\whea_error_type.htm
old-project: whea
ms.assetid: b10dbb47-394c-42f0-9471-6e5deb73a7b9
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: WHEA_ERROR_TYPE, ntddk/WHEA_ERROR_TYPE, WheaErrTypeProcessor, ntddk/WheaErrTypePCIXDevice, WheaErrTypePCIExpress, ntddk/PWHEA_ERROR_TYPE, ntddk/WheaErrTypeMemory, WheaErrTypeGeneric, PWHEA_ERROR_TYPE enumeration pointer [WHEA Drivers and Applications], *PWHEA_ERROR_TYPE, WheaErrTypeNMI, PWHEA_ERROR_TYPE, ntddk/WheaErrTypeGeneric, ntddk/WheaErrTypePCIXBus, ntddk/WheaErrTypeProcessor, _WHEA_ERROR_TYPE, WheaErrTypeMemory, ntddk/WheaErrTypeNMI, whearef_4e585fa6-81e5-4196-b7fa-6194d3701835.xml, WHEA_ERROR_TYPE enumeration [WHEA Drivers and Applications], ntddk/WheaErrTypePCIExpress, WheaErrTypePCIXBus, whea.whea_error_type, WheaErrTypePCIXDevice
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_ERROR_TYPE
product: Windows
targetos: Windows
req.typenames: "*PWHEA_ERROR_TYPE, WHEA_ERROR_TYPE"
---

# _WHEA_ERROR_TYPE enumeration


## -description


The WHEA_ERROR_TYPE enumeration defines the different types of hardware components that can report a hardware error.


## -syntax


````
typedef enum _WHEA_ERROR_TYPE { 
  WheaErrTypeProcessor   = 0,
  WheaErrTypeMemory,
  WheaErrTypePCIExpress,
  WheaErrTypeNMI,
  WheaErrTypePCIXBus,
  WheaErrTypePCIXDevice,
  WheaErrTypeGeneric
} WHEA_ERROR_TYPE, *PWHEA_ERROR_TYPE;
````


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_TYPE enumeration%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

