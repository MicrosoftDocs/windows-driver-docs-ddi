---
UID: NS:miniport._PCI_PMCSR_BSE
title: "_PCI_PMCSR_BSE"
author: windows-driver-content
description: The PCI_PMCSR_BSE structure is used to report the contents of the power management control status register for PCI bridge support extensions.
old-location: pci\pci_pmcsr_bse.htm
tech.root: PCI
ms.assetid: f65116f6-0a61-4609-993b-d7b2eabf12b5
ms.date: 2/24/2018
ms.keywords: "*PPCI_PMCSR_BSE, PCI.pci_pmcsr_bse, PCI_PMCSR_BSE, PCI_PMCSR_BSE structure [Buses], PPCI_PMCSR_BSE, PPCI_PMCSR_BSE structure pointer [Buses], _PCI_PMCSR_BSE, pci_struct_8ff8cc6c-91a4-4396-9d4c-8d99967a9417.xml, wdm/PCI_PMCSR_BSE, wdm/PPCI_PMCSR_BSE"
ms.topic: struct
req.header: miniport.h
req.include-header: Wdm.h, Miniport.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	PCI_PMCSR_BSE
product:
- Windows
targetos: Windows
req.typenames: PCI_PMCSR_BSE, *PPCI_PMCSR_BSE
---

# _PCI_PMCSR_BSE structure


## -description


The PCI_PMCSR_BSE structure is used to report the contents of the power management control status register for PCI bridge support extensions.


## -syntax


```cpp
typedef struct _PCI_PMCSR_BSE {
  UCHAR Rsvd1;
  UCHAR D3HotSupportsStopClock;
  UCHAR BusPowerClockControlEnabled;
} PCI_PMCSR_BSE, *PPCI_PMCSR_BSE;
```


## -struct-fields




### -field Rsvd1

Reserved.


### -field D3HotSupportsStopClock

Indicates how the power state of a secondary bus is affected when the primary bus transitions to a D3 power state. For a detailed explanation of the values in this member and how they affect the relationship between the primary and secondary buses, see the <i>PCI Power Management Specification</i>.


### -field BusPowerClockControlEnabled

Indicates, when 1, that the bus's power clock control mechanism is enabled. A value of 0 indicates that the bus power clock control mechanism is disabled.  For a detailed explanation of the meaning of this member, see the <i>PCI Power Management Specification</i>.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537588">PCI_PM_CAPABILITY</a>



 

 


