---
UID: NS:wdm._PCI_EXPRESS_CORRECTABLE_ERROR_MASK
title: _PCI_EXPRESS_CORRECTABLE_ERROR_MASK (wdm.h)
description: The PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) correctable error mask register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_correctable_error_mask.htm
tech.root: PCI
ms.assetid: d666cdd3-a673-4105-b982-e7cc942131ee
ms.date: 02/24/2018
keywords: ["_PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure"]
ms.keywords: "*PPCI_CORRECTABLE_ERROR_MASK, PCI.pci_express_correctable_error_mask, PCI_EXPRESS_CORRECTABLE_ERROR_MASK, PCI_EXPRESS_CORRECTABLE_ERROR_MASK union [Buses], PPCI_CORRECTABLE_ERROR_MASK, PPCI_CORRECTABLE_ERROR_MASK union pointer [Buses], _PCI_EXPRESS_CORRECTABLE_ERROR_MASK, pci_struct_770185be-12f9-4519-8077-6d90e8344590.xml, wdm/PCI_EXPRESS_CORRECTABLE_ERROR_MASK, wdm/PPCI_CORRECTABLE_ERROR_MASK"
f1_keywords:
 - "wdm/PCI_EXPRESS_CORRECTABLE_ERROR_MASK"
 - "PCI_EXPRESS_CORRECTABLE_ERROR_MASK"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- PCI_EXPRESS_CORRECTABLE_ERROR_MASK
product:
- Windows
targetos: Windows
req.typenames: PCI_EXPRESS_CORRECTABLE_ERROR_MASK, *PPCI_CORRECTABLE_ERROR_MASK
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure


## -description


The PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) correctable error mask register of a PCIe advanced error reporting capability structure.


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


## -struct-fields




### -field DUMMYSTRUCTNAME




### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure.


#### - AdvisoryNonFatalError

A single bit that indicates that the reporting of advisory non-fatal errors is masked.


#### - BadDLLP

A single bit that indicates that the reporting of bad data link layer packets (DLLPs) is masked.


#### - BadTLP

A single bit that indicates that the reporting of bad transaction layer packets (TLPs) is masked.


#### - ReceiverError

A single bit that indicates that the reporting of receiver errors is masked.


#### - ReplayNumRollover

A single bit that indicates that the reporting of rollovers of the counter that counts the number of times the retry buffer has been re-transmitted is masked.


#### - ReplayTimerTimeout

A single bit that indicates that the reporting of timeouts of the replay timer is masked.


#### - Reserved1

Reserved.


#### - Reserved2

Reserved.


#### - Reserved3

Reserved.


## -remarks



The PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure is contained in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structures.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability">PCI_EXPRESS_AER_CAPABILITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>



 

 


