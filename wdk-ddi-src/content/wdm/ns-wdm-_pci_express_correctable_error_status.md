---
UID: NS:wdm._PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
title: _PCI_EXPRESS_CORRECTABLE_ERROR_STATUS (wdm.h)
description: The PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) correctable error status register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_correctable_error_status.htm
tech.root: PCI
ms.date: 02/24/2018
keywords: ["PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure"]
ms.keywords: "*PPCI_CORRECTABLE_ERROR_STATUS, PCI.pci_express_correctable_error_status, PCI_EXPRESS_CORRECTABLE_ERROR_STATUS, PCI_EXPRESS_CORRECTABLE_ERROR_STATUS union [Buses], PPCI_CORRECTABLE_ERROR_STATUS, PPCI_CORRECTABLE_ERROR_STATUS union pointer [Buses], _PCI_EXPRESS_CORRECTABLE_ERROR_STATUS, pci_struct_1366a090-7405-4cd8-b725-19753a248441.xml, wdm/PCI_EXPRESS_CORRECTABLE_ERROR_STATUS, wdm/PPCI_CORRECTABLE_ERROR_STATUS"
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
req.typenames: PCI_EXPRESS_CORRECTABLE_ERROR_STATUS, *PPCI_CORRECTABLE_ERROR_STATUS
req.product: Windows 10 or later.
f1_keywords:
 - _PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
 - wdm/_PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
 - PPCI_CORRECTABLE_ERROR_STATUS
 - wdm/PPCI_CORRECTABLE_ERROR_STATUS
 - PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
 - wdm/PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
---

# _PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure (wdm.h)


## -description

The PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) correctable error status register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure.


#### - AdvisoryNonFatalError

A single bit that indicates that an advisory non-fatal error has occurred.


#### - BadDLLP

A single bit that indicates that a bad data link layer packet (DLLP) error has occurred.


#### - BadTLP

A single bit that indicates that a bad transaction layer packet (TLP) error has occurred.


#### - ReceiverError

A single bit that indicates that a receiver error has occurred.


#### - ReplayNumRollover

A single bit that indicates that the counter that counts the number of times the retry buffer has been re-transmitted has rolled over.


#### - ReplayTimerTimeout

A single bit that indicates that the replay timer has timed out.


#### - Reserved1

Reserved.


#### - Reserved2

Reserved.


#### - Reserved3

Reserved.

## -syntax

```cpp
typedef union _PCI_EXPRESS_CORRECTABLE_ERROR_STATUS {
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
} PCI_EXPRESS_CORRECTABLE_ERROR_STATUS, *PPCI_CORRECTABLE_ERROR_STATUS;
```

## -remarks

The PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure is contained in the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, and <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structures.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability">PCI_EXPRESS_AER_CAPABILITY</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>
