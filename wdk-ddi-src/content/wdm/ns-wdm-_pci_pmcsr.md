---
UID: NS:wdm._PCI_PMCSR
title: "_PCI_PMCSR"
author: windows-driver-content
description: The PCI_PMCSR structure is used to report the contents of the device's power management control status register.
old-location: pci\pci_pmcsr.htm
tech.root: PCI
ms.assetid: 5c4bf4c0-c36f-4779-a012-6364c94f37a1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPCI_PMCSR, PCI.pci_pmcsr, PCI_PMCSR, PCI_PMCSR structure [Buses], PPCI_PMCSR, PPCI_PMCSR structure pointer [Buses], _PCI_PMCSR, pci_struct_03c3c722-9aa9-4fff-a50e-4499122d7490.xml, wdm/PCI_PMCSR, wdm/PPCI_PMCSR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	PCI_PMCSR
product:
- Windows
targetos: Windows
req.typenames: PCI_PMCSR, *PPCI_PMCSR
req.product: Windows 10 or later.
---

# _PCI_PMCSR structure


## -description


The PCI_PMCSR structure is used to report the contents of the device's power management control status register.


## -syntax


```cpp
typedef struct _PCI_PMCSR {
  USHORT PowerState  :2;
  USHORT Rsvd1  :6;
  USHORT PMEEnable  :1;
  USHORT DataSelect  :4;
  USHORT DataScale  :2;
  USHORT PMEStatus  :1;
} PCI_PMCSR, *PPCI_PMCSR;
```


## -struct-fields




### -field PowerState

Indicates the power state of the device. This member can have the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0x00

</td>
<td>
Indicates that the device is in D0.

</td>
</tr>
<tr>
<td>
0x01

</td>
<td>
Indicates that the device is in D1.

</td>
</tr>
<tr>
<td>
0x02

</td>
<td>
Indicates that the device is in D2.

</td>
</tr>
<tr>
<td>
0x03

</td>
<td>
Indicates that the device is in D3.

</td>
</tr>
</table>
 

For more information about the power state register, see the <i>PCI Power Management Specification</i>.


### -field Rsvd1

Reserved.


### -field NoSoftReset




### -field Rsvd2




### -field PMEEnable

Indicates, when 1, that the device is enabled to assert the PME signal. When 0, the device is not enabled to assert the PME signal. For more information about the meaning of the PME Enable bit, see the <i>PCI Power Management Specification</i>.


### -field DataSelect

Indicates which data is to be reported through the data register. For more information about the values that this member can hold, see the <i>PCI Power Management Specification</i>.


### -field DataScale

Indicates the scaling factor used to interpret the value of the data register. For more information about the values that this member can hold, see the <i>PCI Power Management Specification</i>.


### -field PMEStatus

Contains a one-bit value (either 0 or 1) that reports the value of the PMEStatus bit in the power management register. For more information about the values that this member can hold, see the <i>PCI Power Management Specification</i>.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537588">PCI_PM_CAPABILITY</a>



 

 


