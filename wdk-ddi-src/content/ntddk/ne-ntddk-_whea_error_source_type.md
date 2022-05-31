---
UID: NE:ntddk._WHEA_ERROR_SOURCE_TYPE
tech.root: whea
title: WHEA_ERROR_SOURCE_TYPE (ntddk.h)
ms.date: 03/03/2022
targetos: Windows
description: The WHEA_ERROR_SOURCE_TYPE enumeration defines the different types of error sources that can report hardware errors.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntddk.h
req.include-header: Ntddk.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt:
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_ERROR_SOURCE_TYPE
 - PWHEA_ERROR_SOURCE_TYPE
 - WHEA_ERROR_SOURCE_TYPE
f1_keywords:
 - _WHEA_ERROR_SOURCE_TYPE
 - ntddk/_WHEA_ERROR_SOURCE_TYPE
 - PWHEA_ERROR_SOURCE_TYPE
 - ntddk/PWHEA_ERROR_SOURCE_TYPE
 - WHEA_ERROR_SOURCE_TYPE
 - ntddk/WHEA_ERROR_SOURCE_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _WHEA_ERROR_SOURCE_TYPE
---

## -description

The **WHEA_ERROR_SOURCE_TYPE** enumeration defines the different types of error sources that can report hardware errors.

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

Defines the **WheaErrSrcTypeGenericV2** constant.

### -field WheaErrSrcTypeSCIGenericV2

Defines the **WheaErrSrcTypeSCIGenericV2** constant.

### -field WheaErrSrcTypeBMC

A Baseboard Management Controller (BMC) error.

### -field WheaErrSrcTypePMEM

An ARS PMEM error.

### -field WheaErrSrcTypeDeviceDriver

A driver-specific error.

### -field WheaErrSrcTypeSea

Defines the **WheaErrSrcTypeSea** constant.

### -field WheaErrSrcTypeSei

Defines the **WheaErrSrcTypeSei** constant.

### -field WheaErrSrcTypeMax

The maximum number of error source types that can report hardware errors.

## -remarks

The [WHEA_ERROR_SOURCE_DESCRIPTOR](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor) structure contains a member of type WHEA_ERROR_SOURCE_TYPE that specifies the type of error source that is described by the structure.

The [WHEA_ERROR_PACKET](/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)) structure contains a member of type WHEA_ERROR_SOURCE_TYPE that specifies the type of error source that caused the error condition described by the structure.

## -see-also

[Windows Hardware Error Architecture Definitions](/windows-hardware/drivers/whea/windows-hardware-error-architecture-definitions)

[WHEA_ERROR_PACKET](/previous-versions/windows/hardware/drivers/ff560465(v=vs.85))

[WHEA_ERROR_SOURCE_DESCRIPTOR](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor)
