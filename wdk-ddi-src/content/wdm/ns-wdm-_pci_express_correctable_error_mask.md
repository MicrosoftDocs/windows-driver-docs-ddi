---
UID: NS:wdm._PCI_EXPRESS_CORRECTABLE_ERROR_MASK
title: _PCI_EXPRESS_CORRECTABLE_ERROR_MASK (wdm.h)
description: The _PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure (wdm.h) describes a PCI Express (PCIe) correctable error mask register used in advanced error reporting.
old-location: pci\pci_express_correctable_error_mask.htm
tech.root: PCI
ms.date: 02/24/2018
keywords: ["PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure"]
ms.keywords: "*PPCI_CORRECTABLE_ERROR_MASK, PCI.pci_express_correctable_error_mask, PCI_EXPRESS_CORRECTABLE_ERROR_MASK, PCI_EXPRESS_CORRECTABLE_ERROR_MASK union [Buses], PPCI_CORRECTABLE_ERROR_MASK, PPCI_CORRECTABLE_ERROR_MASK union pointer [Buses], _PCI_EXPRESS_CORRECTABLE_ERROR_MASK, pci_struct_770185be-12f9-4519-8077-6d90e8344590.xml, wdm/PCI_EXPRESS_CORRECTABLE_ERROR_MASK, wdm/PPCI_CORRECTABLE_ERROR_MASK"
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h, Miniport.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: PCI_EXPRESS_CORRECTABLE_ERROR_MASK, *PPCI_CORRECTABLE_ERROR_MASK
req.product: Windows 10 or later.
f1_keywords:
 - _PCI_EXPRESS_CORRECTABLE_ERROR_MASK
 - wdm/_PCI_EXPRESS_CORRECTABLE_ERROR_MASK
 - PPCI_CORRECTABLE_ERROR_MASK
 - wdm/PPCI_CORRECTABLE_ERROR_MASK
 - PCI_EXPRESS_CORRECTABLE_ERROR_MASK
 - wdm/PCI_EXPRESS_CORRECTABLE_ERROR_MASK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_CORRECTABLE_ERROR_MASK
 - PPCI_CORRECTABLE_ERROR_MASK
 - PCI_EXPRESS_CORRECTABLE_ERROR_MASK
---

# _PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure (wdm.h)


## -description

The PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) correctable error mask register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME


### -field DUMMYSTRUCTNAME.AdvisoryNonFatalError

A single bit that indicates that the reporting of advisory non-fatal errors is masked.


### -field DUMMYSTRUCTNAME.BadDLLP

A single bit that indicates that the reporting of bad data link layer packets (DLLPs) is masked.


### -field DUMMYSTRUCTNAME.BadTLP

A single bit that indicates that the reporting of bad transaction layer packets (TLPs) is masked.


### -field DUMMYSTRUCTNAME.ReceiverError

A single bit that indicates that the reporting of receiver errors is masked.


### -field DUMMYSTRUCTNAME.ReplayNumRollover

A single bit that indicates that the reporting of rollovers of the counter that counts the number of times the retry buffer has been re-transmitted is masked.


### -field DUMMYSTRUCTNAME.ReplayTimerTimeout

A single bit that indicates that the reporting of timeouts of the replay timer is masked.


### -field DUMMYSTRUCTNAME.Reserved1

Reserved.


### -field DUMMYSTRUCTNAME.Reserved2

Reserved.

### -field DUMMYSTRUCTNAME.CorrectedInternalError

### -field DUMMYSTRUCTNAME.HeaderLogOverflow

### -field DUMMYSTRUCTNAME.Reserved3

Reserved.

### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure.

## -syntax

```cpp
typedef union _PCI_EXPRESS_CORRECTABLE_ERROR_MASK {
  struct {
    ULONG ReceiverError  :1;
    ULONG Reserved1  :5;
    ULONG BadTLP  :1;
    ULONG BadDLLP  :1;
    ULONG ReplayNumRollover  :1;
    ULONG Reserved2  :3;
    ULONG ReplayTimerTimeout  :1;
    ULONG AdvisoryNonFatalError  :1;
    ULONG Reserved3  :18;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_CORRECTABLE_ERROR_MASK, *PPCI_CORRECTABLE_ERROR_MASK;
```

## -remarks

The PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure is contained in the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, and <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structures.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability">PCI_EXPRESS_AER_CAPABILITY</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>

