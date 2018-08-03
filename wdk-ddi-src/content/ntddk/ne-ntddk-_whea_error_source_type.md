---
UID: NE:ntddk._WHEA_ERROR_SOURCE_TYPE
title: "_WHEA_ERROR_SOURCE_TYPE"
author: windows-driver-content
description: The WHEA_ERROR_SOURCE_TYPE enumeration defines the different types of error sources that can report hardware errors.
old-location: whea\whea_error_source_type.htm
tech.root: whea
ms.assetid: d2615320-6c8a-4813-afb5-c5b510e5fde9
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_ERROR_SOURCE_TYPE, PWHEA_ERROR_SOURCE_TYPE, PWHEA_ERROR_SOURCE_TYPE enumeration pointer [WHEA Drivers and Applications], WHEA_ERROR_SOURCE_TYPE, WHEA_ERROR_SOURCE_TYPE enumeration [WHEA Drivers and Applications], WheaErrSrcTypeBOOT, WheaErrSrcTypeCMC, WheaErrSrcTypeCPE, WheaErrSrcTypeGeneric, WheaErrSrcTypeINIT, WheaErrSrcTypeIPFCMC, WheaErrSrcTypeIPFCPE, WheaErrSrcTypeIPFMCA, WheaErrSrcTypeMCE, WheaErrSrcTypeMax, WheaErrSrcTypeNMI, WheaErrSrcTypePCIe, WheaErrSrcTypeSCIGeneric, _WHEA_ERROR_SOURCE_TYPE, ntddk/PWHEA_ERROR_SOURCE_TYPE, ntddk/WHEA_ERROR_SOURCE_TYPE, ntddk/WheaErrSrcTypeBOOT, ntddk/WheaErrSrcTypeCMC, ntddk/WheaErrSrcTypeCPE, ntddk/WheaErrSrcTypeGeneric, ntddk/WheaErrSrcTypeINIT, ntddk/WheaErrSrcTypeIPFCMC, ntddk/WheaErrSrcTypeIPFCPE, ntddk/WheaErrSrcTypeIPFMCA, ntddk/WheaErrSrcTypeMCE, ntddk/WheaErrSrcTypeMax, ntddk/WheaErrSrcTypeNMI, ntddk/WheaErrSrcTypePCIe, ntddk/WheaErrSrcTypeSCIGeneric, whea.whea_error_source_type, whearef_786d549e-14b1-4945-a1ce-23c7112ff0c8.xml"
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
-	WHEA_ERROR_SOURCE_TYPE
product:
- Windows
targetos: Windows
req.typenames: WHEA_ERROR_SOURCE_TYPE, *PWHEA_ERROR_SOURCE_TYPE
---

# _WHEA_ERROR_SOURCE_TYPE enumeration


## -description


The WHEA_ERROR_SOURCE_TYPE enumeration defines the different types of error sources that can report hardware errors.


## -enum-fields




### -field WheaErrSrcTypeMCE

A machine check exception (MCE).


### -field WheaErrSrcTypeCMC

A corrected machine check (CMC).


### -field WheaErrSrcTypeCPE

A corrected platform error (CPE).


### -field WheaErrSrcTypeNMI

A nonmaskable interrupt (NMI).


### -field WheaErrSrcTypePCIe

A PCI Express (PCIe) error.


### -field WheaErrSrcTypeGeneric

A type of error source that does not conform to any of the other WHEA_ERROR_SOURCE_TYPE enumeration values.


### -field WheaErrSrcTypeINIT

An Itanium processor INIT error.


### -field WheaErrSrcTypeBOOT

A boot error source.


### -field WheaErrSrcTypeSCIGeneric

A service control interrupt (SCI).


### -field WheaErrSrcTypeIPFMCA

An Itanium processor machine check abort (MCA).


### -field WheaErrSrcTypeIPFCMC

An Itanium processor corrected machine check (CMC).


### -field WheaErrSrcTypeIPFCPE

An Itanium processor corrected platform error (CPE).


### -field WheaErrSrcTypeGenericV2


### -field WheaErrSrcTypeSCIGenericV2


### -field WheaErrSrcTypeMax

The maximum number of error source types that can report hardware errors.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure contains a member of type WHEA_ERROR_SOURCE_TYPE that specifies the type of error source that is described by the structure.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a> structure contains a member of type WHEA_ERROR_SOURCE_TYPE that specifies the type of error source that caused the error condition described by the structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a>
 

 

