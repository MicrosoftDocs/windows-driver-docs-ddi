---
UID: NS:ntddk._WHEA_AER_BRIDGE_DESCRIPTOR
title: "_WHEA_AER_BRIDGE_DESCRIPTOR"
author: windows-driver-content
description: The WHEA_AER_BRIDGE_DESCRIPTOR structure describes a PCI Express (PCIe) bridge error source.
old-location: whea\whea_aer_bridge_descriptor.htm
old-project: whea
ms.assetid: 33cc9d34-cffb-410d-9948-37c8a409e0a5
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: ntddk/WHEA_AER_BRIDGE_DESCRIPTOR, WHEA_AER_BRIDGE_DESCRIPTOR, *PWHEA_AER_BRIDGE_DESCRIPTOR, PWHEA_AER_BRIDGE_DESCRIPTOR, _WHEA_AER_BRIDGE_DESCRIPTOR, ntddk/PWHEA_AER_BRIDGE_DESCRIPTOR, PWHEA_AER_BRIDGE_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_AER_BRIDGE_DESCRIPTOR structure [WHEA Drivers and Applications], whea.whea_aer_bridge_descriptor, whearef_52e2fbef-c8d7-42c8-b8ae-584fbc4f622f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
-	ntddk.h
apiname:
-	WHEA_AER_BRIDGE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: WHEA_AER_BRIDGE_DESCRIPTOR, *PWHEA_AER_BRIDGE_DESCRIPTOR
---

# _WHEA_AER_BRIDGE_DESCRIPTOR structure


## -description


The WHEA_AER_BRIDGE_DESCRIPTOR structure describes a PCI Express (PCIe) bridge error source.


## -syntax


````
typedef struct _WHEA_AER_BRIDGE_DESCRIPTOR {
  USHORT                      Type;
  BOOLEAN                     Enabled;
  UCHAR                       Reserved;
  ULONG                       BusNumber;
  WHEA_PCI_SLOT_NUMBER        Slot;
  USHORT                      DeviceControl;
  AER_BRIDGE_DESCRIPTOR_FLAGS Flags;
  ULONG                       UncorrectableErrorMask;
  ULONG                       UncorrectableErrorSeverity;
  ULONG                       CorrectableErrorMask;
  ULONG                       AdvancedCapsAndControl;
  ULONG                       SecondaryUncorrectableErrorMask;
  ULONG                       SecondaryUncorrectableErrorSev;
  ULONG                       SecondaryCapsAndControl;
} WHEA_AER_BRIDGE_DESCRIPTOR, *PWHEA_AER_BRIDGE_DESCRIPTOR;
````


## -struct-fields




### -field Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_AERBRIDGE.


### -field Enabled

A Boolean value that indicates if the error source is enabled.


### -field Reserved

Reserved for system use.


### -field BusNumber

The bridge's primary bus number.


### -field Slot

A <a href="..\ntddk\ns-ntddk-_whea_pci_slot_number.md">WHEA_PCI_SLOT_NUMBER</a> structure that describes the logical PCI slot where the bridge is located in the system.


### -field DeviceControl

The contents of the bridge's Device Control register.


### -field Flags

An AER_BRIDGE_DESCRIPTOR_FLAGS union that indicates which of the members of the WHEA_AER_BRIDGE_DESCRIPTOR structure can be written to by the operating system. The AER_BRIDGE_DESCRIPTOR_FLAGS union is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _AER_BRIDGE_DESCRIPTOR_FLAGS {
  struct {
    USHORT  UncorrectableErrorMaskRW:1;
    USHORT  UncorrectableErrorSeverityRW:1;
    USHORT  CorrectableErrorMaskRW:1;
    USHORT  AdvancedCapsAndControlRW:1;
    USHORT  SecondaryUncorrectableErrorMaskRW:1;
    USHORT  SecondaryUncorrectableErrorSevRW:1;
    USHORT  SecondaryCapsAndControlRW:1;
    USHORT  Reserved:9;
  };
  USHORT  AsUSHORT;
} AER_BRIDGE_DESCRIPTOR_FLAGS, *PAER_BRIDGE_DESCRIPTOR_FLAGS</pre>
</td>
</tr>
</table></span></div>




#### UncorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the <b>UncorrectableErrorMask</b> member of the WHEA_AER_BRIDGE_DESCRIPTOR structure.



#### UncorrectableErrorSeverityRW

A single bit that indicates that the operating system can write to the <b>UncorrectableErrorSeverity</b> member of the WHEA_AER_BRIDGE_DESCRIPTOR structure.



#### CorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the <b>CorrectableErrorMask</b> member of the WHEA_AER_BRIDGE_DESCRIPTOR structure.



#### AdvancedCapsAndControlRW

A single bit that indicates that the operating system can write to the <b>AdvancedCapsAndControl</b> member of the WHEA_AER_BRIDGE_DESCRIPTOR structure.



#### SecondaryUncorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the <b>SecondaryUncorrectableErrorMask</b> member of the WHEA_AER_BRIDGE_DESCRIPTOR structure.



#### SecondaryUncorrectableErrorSevRW

A single bit that indicates that the operating system can write to the <b>SecondaryUncorrectableErrorSev</b> member of the WHEA_AER_BRIDGE_DESCRIPTOR structure.



#### SecondaryCapsAndControlRW

A single bit that indicates that the operating system can write to the <b>SecondaryCapsAndControl</b> member of the WHEA_AER_BRIDGE_DESCRIPTOR structure.



#### Reserved

Reserved for system use.



#### AsUSHORT

A USHORT representation of the contents of the AER_ROOTPORT_DESCRIPTOR_FLAGS union.


### -field UncorrectableErrorMask

The contents of the bridge's Uncorrectable Error Mask register.


### -field UncorrectableErrorSeverity

The contents of the bridge's Uncorrectable Error Severity register.


### -field CorrectableErrorMask

The contents of the bridge's Correctable Error Mask register.


### -field AdvancedCapsAndControl

The contents of the bridge's Advanced Error Capabilities and Control register.


### -field SecondaryUncorrectableErrorMask

The contents of the bridge's Secondary Uncorrectable Error Mask register.


### -field SecondaryUncorrectableErrorSev

The contents of the bridge's Secondary Uncorrectable Error Severity register.


### -field SecondaryCapsAndControl

The contents of the bridge's Secondary Error Capabilities and Control register.


## -remarks



A WHEA_AER_BRIDGE_DESCRIPTOR structure is contained within the <a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="..\ntddk\ns-ntddk-_whea_pci_slot_number.md">WHEA_PCI_SLOT_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_AER_BRIDGE_DESCRIPTOR structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

