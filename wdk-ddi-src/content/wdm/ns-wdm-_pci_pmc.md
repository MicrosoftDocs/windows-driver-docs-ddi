---
UID: NS:wdm._PCI_PMC
title: _PCI_PMC
author: windows-driver-content
description: The PCI_PMC structure is used to report the contents of the power management capabilities register.
old-location: pci\pci_pmc.htm
old-project: PCI
ms.assetid: e6ec18a3-2da6-4b3a-afe3-17435463fd39
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _PCI_PMC, PCI_PMC, *PPCI_PMC
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
req.alt-api: PCI_PMC
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
req.typenames: PCI_PMC, *PPCI_PMC
req.product: Windows 10 or later.
---

# _PCI_PMC structure



## -description
The PCI_PMC structure is used to report the contents of the power management capabilities register. 



## -syntax

````
typedef struct _PCI_PMC {
  UCHAR              Version  :3;
  UCHAR              PMEClock  :1;
  UCHAR              Rsvd1  :1;
  UCHAR              DeviceSpecificInitialization  :1;
  UCHAR              Rsvd2  :2;
  struct _PM_SUPPORT {
    UCHAR Rsvd2  :1;
    UCHAR D1  :1;
    UCHAR D2  :1;
    UCHAR PMED0  :1;
    UCHAR PMED1  :1;
    UCHAR PMED2  :1;
    UCHAR PMED3Hot  :1;
    UCHAR PMED3Cold  :1;
  } Support;
} PCI_PMC, *PPCI_PMC;
````


## -struct-fields

### -field Version

Contains a 3-bit integer that indicates the version of the <i>PCI Power Management Interface Specification </i>that the device complies with. For a list of values that can be assigned to this member, see the <i>PCI Local Bus Specification</i>. 


### -field PMEClock

Indicates, when 1, that the device relies on the presence of the PCI clock for operation of the PME signal. When this member is a "0", no PCI clock is required to generate the PME signal. 


### -field Rsvd1

Reserved. 


### -field DeviceSpecificInitialization

Indicates when 1 that the device requires a special initialization. For more information about this value, see the <i>PCI Local Bus Specification</i>.


### -field Rsvd2

Reserved. 


### -field Support


### -field Rsvd2

Reserved. 


### -field D1

Reserved. 


### -field D2

Reserved. 


### -field PMED0

Indicates that the device can assert the PME signal from D0. 


### -field PMED1

Indicates that the device can assert the PME signal from D1. 


### -field PMED2

Indicates that the device can assert the PME signal from D2. 


### -field PMED3Hot

Indicates that the device can assert the PME signal from D3. 


### -field PMED3Cold

Indicates that the device can assert the PME signal from D3. 

</dd>
</dl>

## -remarks
The power management capabilities register, whose contents are reported in the PCI_PMC structure, provides information about the power management capabilities of the device. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537588">PCI_PM_CAPABILITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_PMC structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

