---
UID: NS:ntddk._WHEA_AER_ENDPOINT_DESCRIPTOR
title: "_WHEA_AER_ENDPOINT_DESCRIPTOR"
author: windows-driver-content
description: The WHEA_AER_ENDPOINT_DESCRIPTOR structure describes a PCI Express (PCIe) endpoint error source.
old-location: whea\whea_aer_endpoint_descriptor.htm
old-project: whea
ms.assetid: 2b77853d-2c34-4902-90e3-b9a58d56e88e
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: ntddk/WHEA_AER_ENDPOINT_DESCRIPTOR, WHEA_AER_ENDPOINT_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_AER_ENDPOINT_DESCRIPTOR, *PWHEA_AER_ENDPOINT_DESCRIPTOR, PWHEA_AER_ENDPOINT_DESCRIPTOR, whearef_06cb1486-51b0-457d-a0d0-b902c6c43cfc.xml, ntddk/PWHEA_AER_ENDPOINT_DESCRIPTOR, whea.whea_aer_endpoint_descriptor, PWHEA_AER_ENDPOINT_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_AER_ENDPOINT_DESCRIPTOR
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
-	WHEA_AER_ENDPOINT_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PWHEA_AER_ENDPOINT_DESCRIPTOR, WHEA_AER_ENDPOINT_DESCRIPTOR"
---

# _WHEA_AER_ENDPOINT_DESCRIPTOR structure


## -description


The WHEA_AER_ENDPOINT_DESCRIPTOR structure describes a PCI Express (PCIe) endpoint error source.


## -syntax


````
typedef struct _WHEA_AER_ENDPOINT_DESCRIPTOR {
  USHORT                        Type;
  BOOLEAN                       Enabled;
  UCHAR                         Reserved;
  ULONG                         BusNumber;
  WHEA_PCI_SLOT_NUMBER          Slot;
  USHORT                        DeviceControl;
  AER_ENDPOINT_DESCRIPTOR_FLAGS Flags;
  ULONG                         UncorrectableErrorMask;
  ULONG                         UncorrectableErrorSeverity;
  ULONG                         CorrectableErrorMask;
  ULONG                         AdvancedCapsAndControl;
} WHEA_AER_ENDPOINT_DESCRIPTOR, *PWHEA_AER_ENDPOINT_DESCRIPTOR;
````


## -struct-fields




### -field Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_AERENDPOINT.


### -field Enabled

A Boolean value that indicates if the error source is enabled.


### -field Reserved

Reserved for system use.


### -field BusNumber

The endpoint's bus number.


### -field Slot

A <a href="..\ntddk\ns-ntddk-_whea_pci_slot_number.md">WHEA_PCI_SLOT_NUMBER</a> structure that describes the logical PCI slot where the endpoint is located in the system.


### -field DeviceControl

The contents of the endpoint's Device Control register.


### -field Flags

An AER_ENDPOINT_DESCRIPTOR_FLAGS union that indicates which of the members of the WHEA_AER_ENDPOINT_DESCRIPTOR structure can be written to by the operating system. The AER_ENDPOINT_DESCRIPTOR_FLAGS union is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _AER_ENDPOINT_DESCRIPTOR_FLAGS {
  struct {
    USHORT  UncorrectableErrorMaskRW:1;
    USHORT  UncorrectableErrorSeverityRW:1;
    USHORT  CorrectableErrorMaskRW:1;
    USHORT  AdvancedCapsAndControlRW:1;
    USHORT  Reserved:12;
  };
  USHORT  AsUSHORT;
} AER_ENDPOINT_DESCRIPTOR_FLAGS, *PAER_ENDPOINT_DESCRIPTOR_FLAGS</pre>
</td>
</tr>
</table></span></div>




#### UncorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the <b>UncorrectableErrorMask</b> member of the WHEA_AER_ENDPOINT_DESCRIPTOR structure.



#### UncorrectableErrorSeverityRW

A single bit that indicates that the operating system can write to the <b>UncorrectableErrorSeverity</b> member of the WHEA_AER_ENDPOINT_DESCRIPTOR structure.



#### CorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the <b>CorrectableErrorMask</b> member of the WHEA_AER_ENDPOINT_DESCRIPTOR structure.



#### AdvancedCapsAndControlRW

A single bit that indicates that the operating system can write to the <b>AdvancedCapsAndControl</b> member of the WHEA_AER_ENDPOINT_DESCRIPTOR structure.



#### Reserved

Reserved for system use.



#### AsUSHORT

A USHORT representation of the contents of the AER_ENDPOINT_DESCRIPTOR_FLAGS union.


### -field UncorrectableErrorMask

The contents of the endpoint's Uncorrectable Error Mask register.


### -field UncorrectableErrorSeverity

The contents of the endpoint's Uncorrectable Error Severity register.


### -field CorrectableErrorMask

The contents of the endpoint's Correctable Error Mask register.


### -field AdvancedCapsAndControl

The contents of the endpoint's Advanced Error Capabilities and Control register.


## -remarks



A WHEA_AER_ENDPOINT_DESCRIPTOR structure is contained within the <a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="..\ntddk\ns-ntddk-_whea_pci_slot_number.md">WHEA_PCI_SLOT_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_AER_ENDPOINT_DESCRIPTOR structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

