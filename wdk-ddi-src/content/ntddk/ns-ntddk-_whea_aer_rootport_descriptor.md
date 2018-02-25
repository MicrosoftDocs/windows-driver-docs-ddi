---
UID: NS:ntddk._WHEA_AER_ROOTPORT_DESCRIPTOR
title: "_WHEA_AER_ROOTPORT_DESCRIPTOR"
author: windows-driver-content
description: The WHEA_AER_ROOTPORT_DESCRIPTOR structure describes a PCI Express (PCIe) root port error source.
old-location: whea\whea_aer_rootport_descriptor.htm
old-project: whea
ms.assetid: 0c92e8d5-eb98-4789-a221-ebf891cd3876
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , *, *PWHEA_AER_ROOTPORT_DESCRIPTOR, ,, A, C, D, E, H, I, O, P, PWHEA_AER_ROOTPORT_DESCRIPTOR, PWHEA_AER_ROOTPORT_DESCRIPTOR structure pointer [WHEA Drivers and Applications], R, S, T, W, WHEA_AER_ROOTPORT_DESCRIPTOR, WHEA_AER_ROOTPORT_DESCRIPTOR structure [WHEA Drivers and Applications], _, _WHEA_AER_ROOTPORT_DESCRIPTOR, ntddk/PWHEA_AER_ROOTPORT_DESCRIPTOR, ntddk/WHEA_AER_ROOTPORT_DESCRIPTOR, whea.whea_aer_rootport_descriptor, whearef_e96777a4-ff19-4291-9730-ffe4c9828381.xml"
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
-	WHEA_AER_ROOTPORT_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: WHEA_AER_ROOTPORT_DESCRIPTOR, *PWHEA_AER_ROOTPORT_DESCRIPTOR
---

# _WHEA_AER_ROOTPORT_DESCRIPTOR structure


## -description


The WHEA_AER_ROOTPORT_DESCRIPTOR structure describes a PCI Express (PCIe) root port error source.


## -syntax


````
typedef struct _WHEA_AER_ROOTPORT_DESCRIPTOR {
  USHORT                        Type;
  BOOLEAN                       Enabled;
  UCHAR                         Reserved;
  ULONG                         BusNumber;
  WHEA_PCI_SLOT_NUMBER          Slot;
  USHORT                        DeviceControl;
  AER_ROOTPORT_DESCRIPTOR_FLAGS Flags;
  ULONG                         UncorrectableErrorMask;
  ULONG                         UncorrectableErrorSeverity;
  ULONG                         CorrectableErrorMask;
  ULONG                         AdvancedCapsAndControl;
  ULONG                         RootErrorCommand;
} WHEA_AER_ROOTPORT_DESCRIPTOR, *PWHEA_AER_ROOTPORT_DESCRIPTOR;
````


## -struct-fields




### -field Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_AERROOTPORT.


### -field Enabled

A Boolean value that indicates if the error source is enabled.


### -field Reserved

Reserved for system use.


### -field BusNumber

The root port's bus number.


### -field Slot

A <a href="..\ntddk\ns-ntddk-_whea_pci_slot_number.md">WHEA_PCI_SLOT_NUMBER</a> structure that describes the logical PCI slot where the root port is located in the system.


### -field DeviceControl

The contents of the root port's Device Control register.


### -field Flags

An AER_ROOTPORT_DESCRIPTOR_FLAGS union that indicates which of the members of the WHEA_AER_ROOTPORT_DESCRIPTOR structure can be written to by the operating system. The AER_ROOTPORT_DESCRIPTOR_FLAGS union is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _AER_ROOTPORT_DESCRIPTOR_FLAGS {
  struct {
    USHORT  UncorrectableErrorMaskRW:1;
    USHORT  UncorrectableErrorSeverityRW:1;
    USHORT  CorrectableErrorMaskRW:1;
    USHORT  AdvancedCapsAndControlRW:1;
    USHORT  RootErrorCommandRW:1;
    USHORT  Reserved:11;
  };
  USHORT  AsUSHORT;
} AER_ROOTPORT_DESCRIPTOR_FLAGS, *PAER_ROOTPORT_DESCRIPTOR_FLAGS</pre>
</td>
</tr>
</table></span></div>




#### UncorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the <b>UncorrectableErrorMask</b> member of the WHEA_AER_ROOTPORT_DESCRIPTOR structure.



#### UncorrectableErrorSeverityRW

A single bit that indicates that the operating system can write to the <b>UncorrectableErrorSeverity </b>member of the WHEA_AER_ROOTPORT_DESCRIPTOR structure.



#### CorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the <b>CorrectableErrorMask</b> member of the WHEA_AER_ROOTPORT_DESCRIPTOR structure.



#### AdvancedCapsAndControlRW

A single bit that indicates that the operating system can write to the <b>AdvancedCapsAndControl</b> member of the WHEA_AER_ROOTPORT_DESCRIPTOR structure.



#### RootErrorCommandRW

A single bit that indicates that the operating system can write to the <b>RootErrorCommand</b> member of the WHEA_AER_ROOTPORT_DESCRIPTOR structure.



#### Reserved

Reserved for system use.



#### AsUSHORT

A USHORT representation of the contents of the AER_ROOTPORT_DESCRIPTOR_FLAGS union.


### -field UncorrectableErrorMask

The contents of the root port's Uncorrectable Error Mask register.


### -field UncorrectableErrorSeverity

The contents of the root port's Uncorrectable Error Severity register.


### -field CorrectableErrorMask

The contents of the root port's Correctable Error Mask register.


### -field AdvancedCapsAndControl

The contents of the root port's Advanced Error Capabilities and Control register.


### -field RootErrorCommand

The contents of the root port's Root Error Command register.


## -remarks



A WHEA_AER_ROOTPORT_DESCRIPTOR structure is contained within the <a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_pci_slot_number.md">WHEA_PCI_SLOT_NUMBER</a>



<a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_AER_ROOTPORT_DESCRIPTOR structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

