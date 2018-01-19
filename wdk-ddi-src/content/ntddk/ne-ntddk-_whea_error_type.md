---
UID: NE:ntddk._WHEA_ERROR_TYPE
title: _WHEA_ERROR_TYPE
author: windows-driver-content
description: The WHEA_ERROR_TYPE enumeration defines the different types of hardware components that can report a hardware error.
old-location: whea\whea_error_type.htm
old-project: whea
ms.assetid: b10dbb47-394c-42f0-9471-6e5deb73a7b9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WHEA_ERROR_TYPE, *PWHEA_ERROR_TYPE, WHEA_ERROR_TYPE
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
req.alt-api: WHEA_ERROR_TYPE
req.alt-loc: ntddk.h
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
req.typenames: *PWHEA_ERROR_TYPE, WHEA_ERROR_TYPE
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
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_TYPE enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

