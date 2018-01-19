---
UID: NS:wdm._PCI_PMCSR
title: _PCI_PMCSR
author: windows-driver-content
description: The PCI_PMCSR structure is used to report the contents of the device's power management control status register.
old-location: pci\pci_pmcsr.htm
old-project: PCI
ms.assetid: 5c4bf4c0-c36f-4779-a012-6364c94f37a1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _PCI_PMCSR, *PPCI_PMCSR, PCI_PMCSR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCI_PMCSR
req.alt-loc: wdm.h
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
req.typenames: *PPCI_PMCSR, PCI_PMCSR
req.product: Windows 10 or later.
---

# _PCI_PMCSR structure



## -description
The PCI_PMCSR structure is used to report the contents of the device's power management control status register. 



## -syntax

````
typedef struct _PCI_PMCSR {
  USHORT PowerState  :2;
  USHORT Rsvd1  :6;
  USHORT PMEEnable  :1;
  USHORT DataSelect  :4;
  USHORT DataScale  :2;
  USHORT PMEStatus  :1;
} PCI_PMCSR, *PPCI_PMCSR;
````


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


### -field PMEEnable

Indicates, when 1, that the device is enabled to assert the PME signal. When 0, the device is not enabled to assert the PME signal. For more information about the meaning of the PME Enable bit, see the <i>PCI Power Management Specification</i>. 


### -field DataSelect

Indicates which data is to be reported through the data register. For more information about the values that this member can hold, see the <i>PCI Power Management Specification</i>. 


### -field DataScale

Indicates the scaling factor used to interpret the value of the data register. For more information about the values that this member can hold, see the <i>PCI Power Management Specification</i>. 


### -field PMEStatus

Contains a one-bit value (either 0 or 1) that reports the value of the PMEStatus bit in the power management register. For more information about the values that this member can hold, see the <i>PCI Power Management Specification</i>. 


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537588">PCI_PM_CAPABILITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_PMCSR structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

