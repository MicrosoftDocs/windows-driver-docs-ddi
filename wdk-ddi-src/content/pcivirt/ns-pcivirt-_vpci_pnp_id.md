---
UID: NS:pcivirt._VPCI_PNP_ID
title: "_VPCI_PNP_ID"
author: windows-driver-content
description: Stores the PnP identifiers for a virtual PCI device. For example strings, see Identifiers for PCI Devices.
old-location: pci\vpci_pnp_id.htm
tech.root: PCI
ms.assetid: 9759ed77-d91a-466b-9678-4ed4fb4359e4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PVPCI_PNP_ID, PCI.vpci_pnp_id, VPCI_PNP_ID, VPCI_PNP_ID structure [Buses], _VPCI_PNP_ID, pcivirt/VPCI_PNP_ID"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pcivirt.h
req.include-header:
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Pcivirt.h
api_name:
-	VPCI_PNP_ID
product:
- Windows
targetos: Windows
req.typenames: VPCI_PNP_ID, *PVPCI_PNP_ID
---

# _VPCI_PNP_ID structure


## -description


Stores the PnP identifiers for a virtual PCI device. For example strings, see <a href="https://docs.microsoft.com/windows-hardware/drivers/install/identifiers-for-pci-devices">Identifiers for PCI Devices</a>.


## -syntax


```cpp
typedef struct _VPCI_PNP_ID {
  USHORT  VendorID;
  USHORT  DeviceID;
  UCHAR   RevisionID;
  UCHAR   ProgIf;
  UCHAR   SubClass;
  UCHAR   BaseClass;
  USHORT  SubVendorID;
  USHORT  SubSystemID;
} VPCI_PNP_ID, VPCI_PNP_ID;
```


## -struct-fields




### -field VendorID

PCI SIG-assigned identifier for the vendor of the device.


### -field DeviceID

Vendor-defined identifier for the device.


### -field RevisionID

Vendor-defined revision number.


### -field ProgIf

Programming Interface code.


### -field SubClass

Vendor-defined subclass code.


### -field BaseClass

Vendor-defined base class code from the configuration space.


### -field SubVendorID

PCI SIG-assigned identifier for the vendor of the subsystem.


### -field SubSystemID

Vendor-defined subsystem identifier.


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/install/identifiers-for-pci-devices">Identifiers for PCI Devices</a>



 

 


