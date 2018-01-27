---
UID: NS:pcivirt._VPCI_PNP_ID
title: _VPCI_PNP_ID
author: windows-driver-content
description: Stores the PnP identifiers for a virtual PCI device. For example strings, see Identifiers for PCI Devices.
old-location: pci\vpci_pnp_id.htm
old-project: PCI
ms.assetid: 9759ed77-d91a-466b-9678-4ed4fb4359e4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VPCI_PNP_ID, PCI.vpci_pnp_id, *PVPCI_PNP_ID, _VPCI_PNP_ID, pcivirt/VPCI_PNP_ID, VPCI_PNP_ID structure [Buses]
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Pcivirt.h
apiname: 
-	VPCI_PNP_ID
product: Windows
targetos: Windows
req.typenames: *PVPCI_PNP_ID, VPCI_PNP_ID
---

# _VPCI_PNP_ID structure


## -description


Stores the PnP identifiers for a virtual PCI device. For example strings, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/identifiers-for-pci-devices">Identifiers for PCI Devices</a>.


## -syntax


````
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
````


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

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/identifiers-for-pci-devices">Identifiers for PCI Devices</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20VPCI_PNP_ID structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

