---
UID: NS:miniport._PCI_EXPRESS_PME_REQUESTOR_ID
title: PCI_EXPRESS_PME_REQUESTOR_ID (miniport.h)
description: The _PCI_EXPRESS_PME_REQUESTOR_ID union (miniport.h) describes the identifier of the requester of a power management event (PME).
tech.root: PCI
ms.date: 07/18/2022
keywords: ["PCI_EXPRESS_PME_REQUESTOR_ID structure"]
ms.keywords: "*PPCI_EXPRESS_PME_REQUESTOR_ID, PCI.pci_express_pme_requestor_id, PCI_EXPRESS_PME_REQUESTOR_ID, PCI_EXPRESS_PME_REQUESTOR_ID union [Buses], PPCI_EXPRESS_PME_REQUESTOR_ID, PPCI_EXPRESS_PME_REQUESTOR_ID union pointer [Buses], _PCI_EXPRESS_PME_REQUESTOR_ID, ntddk/PCI_EXPRESS_PME_REQUESTOR_ID, ntddk/PPCI_EXPRESS_PME_REQUESTOR_ID, pci_struct_0cb11d1f-7426-42fc-9d77-373516a492ae.xml"
req.header: miniport.h
req.include-header: Ntddk.h, Miniport.h
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
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: PCI_EXPRESS_PME_REQUESTOR_ID, *PPCI_EXPRESS_PME_REQUESTOR_ID
f1_keywords:
 - _PCI_EXPRESS_PME_REQUESTOR_ID
 - miniport/_PCI_EXPRESS_PME_REQUESTOR_ID
 - PPCI_EXPRESS_PME_REQUESTOR_ID
 - miniport/PPCI_EXPRESS_PME_REQUESTOR_ID
 - PCI_EXPRESS_PME_REQUESTOR_ID
 - miniport/PCI_EXPRESS_PME_REQUESTOR_ID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_PME_REQUESTOR_ID
 - PPCI_EXPRESS_PME_REQUESTOR_ID
 - PCI_EXPRESS_PME_REQUESTOR_ID
---

## -description

The **PCI_EXPRESS_PME_REQUESTOR_ID** union describes the identifier of the requester of a power management event (PME).

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.FunctionNumber

The function number of the requester.

### -field DUMMYSTRUCTNAME.DeviceNumber

The device number of the requester.

### -field DUMMYSTRUCTNAME.BusNumber

The bus number of the requester.

### -field AsUSHORT

A USHORT representation of the contents of the **PCI_EXPRESS_PME_REQUESTOR_ID** structure.

## -remarks

The **PCI_EXPRESS_PME_REQUESTOR_ID** structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_PME_REQUESTOR_ID structure is contained in the **PMERequestorId** member of the [PCI_EXPRESS_ROOT_STATUS_REGISTER](../ntddk/ns-ntddk-_pci_express_root_status_register.md) structure.

## -see-also

[PCI_EXPRESS_ROOT_STATUS_REGISTER](../ntddk/ns-ntddk-_pci_express_root_status_register.md)