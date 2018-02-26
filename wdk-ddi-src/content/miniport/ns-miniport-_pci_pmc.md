---
UID: NS:miniport._PCI_PMC
title: "_PCI_PMC"
author: windows-driver-content
description: The PCI_PMC structure is used to report the contents of the power management capabilities register.
old-location: pci\pci_pmc.htm
old-project: PCI
ms.assetid: e6ec18a3-2da6-4b3a-afe3-17435463fd39
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PPCI_PMC, ,, C, I, M, P, PCI.pci_pmc, PCI_PMC, PCI_PMC structure [Buses], PPCI_PMC, PPCI_PMC structure pointer [Buses], _, _PCI_PMC, pci_struct_5ac33692-66a0-4c2e-89dc-e5ace757e06b.xml, wdm/PCI_PMC, wdm/PPCI_PMC"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	PCI_PMC
product: Windows
targetos: Windows
req.typenames: PCI_PMC, *PPCI_PMC
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



#### Rsvd2

Reserved. 



#### D1

Reserved. 



#### D2

Reserved. 



#### PMED0

Indicates that the device can assert the PME signal from D0. 



#### PMED1

Indicates that the device can assert the PME signal from D1. 



#### PMED2

Indicates that the device can assert the PME signal from D2. 



#### PMED3Hot

Indicates that the device can assert the PME signal from D3. 



#### PMED3Cold

Indicates that the device can assert the PME signal from D3. 


### -field _PM_SUPPORT

 




## -remarks



The power management capabilities register, whose contents are reported in the PCI_PMC structure, provides information about the power management capabilities of the device. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537588">PCI_PM_CAPABILITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_PMC structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

