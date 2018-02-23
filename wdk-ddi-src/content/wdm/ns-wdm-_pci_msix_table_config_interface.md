---
UID: NS:wdm._PCI_MSIX_TABLE_CONFIG_INTERFACE
title: "_PCI_MSIX_TABLE_CONFIG_INTERFACE"
author: windows-driver-content
description: The PCI_MSIX_TABLE_CONFIG_INTERFACE structure enables device drivers to modify their MSI-X interrupt settings. This structure describes the GUID_MSIX_TABLE_CONFIG_INTERFACE interface.
old-location: kernel\pci_msix_table_config_interface.htm
old-project: kernel
ms.assetid: 0809a963-a0e7-49ca-b483-c39f1606051e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PCI_MSIX_TABLE_CONFIG_INTERFACE structure [Kernel-Mode Driver Architecture], kernel.pci_msix_table_config_interface, PPCI_MSIX_TABLE_CONFIG_INTERFACE structure pointer [Kernel-Mode Driver Architecture], PPCI_MSIX_TABLE_CONFIG_INTERFACE, PCI_MSIX_TABLE_CONFIG_INTERFACE, wdm/PCI_MSIX_TABLE_CONFIG_INTERFACE, *PPCI_MSIX_TABLE_CONFIG_INTERFACE, drvr_interface_86de1cfb-1eac-442b-a154-6f23fcab87cd.xml, wdm/PPCI_MSIX_TABLE_CONFIG_INTERFACE, _PCI_MSIX_TABLE_CONFIG_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista with Service Pack 1 (SP1), Windows Server 2008, and later versions of the Windows operating system.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	PCI_MSIX_TABLE_CONFIG_INTERFACE
product: Windows
targetos: Windows
req.typenames: PCI_MSIX_TABLE_CONFIG_INTERFACE, *PPCI_MSIX_TABLE_CONFIG_INTERFACE
req.product: Windows 10 or later.
---

# _PCI_MSIX_TABLE_CONFIG_INTERFACE structure


## -description


The <b>PCI_MSIX_TABLE_CONFIG_INTERFACE</b> structure enables device drivers to modify their MSI-X interrupt settings. This structure  describes the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff558787">GUID_MSIX_TABLE_CONFIG_INTERFACE</a> interface.


## -syntax


````
typedef struct _PCI_MSIX_TABLE_CONFIG_INTERFACE {
  USHORT                     Size;
  USHORT                     Version;
  PVOID                      Context;
  PINTERFACE_REFERENCE       InterfaceReference;
  PINTERFACE_DEREFERENCE     InterfaceDereference;
  PPCI_MSIX_SET_ENTRY        SetTableEntry;
  PPCI_MSIX_MASKUNMASK_ENTRY MaskTableEntry;
  PPCI_MSIX_MASKUNMASK_ENTRY UnmaskTableEntry;
  PPCI_MSIX_GET_ENTRY        GetTableEntry;
  PPCI_MSIX_GET_TABLE_SIZE   GetTableSize;
} PCI_MSIX_TABLE_CONFIG_INTERFACE, *PPCI_MSIX_TABLE_CONFIG_INTERFACE;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The driver-defined interface version.


### -field Context

A pointer to interface-specific context information. 


### -field InterfaceReference

A pointer to an <a href="..\wudfwdm\nc-wudfwdm-pinterface_reference.md">InterfaceReference</a> routine that increments the interface's reference count.


### -field InterfaceDereference

A pointer to an <a href="..\wudfwdm\nc-wudfwdm-pinterface_dereference.md">InterfaceDereference</a> routine that decrements the interface's reference count.


### -field SetTableEntry

A pointer to the interface's <a href="..\wdm\nc-wdm-pci_msix_set_entry.md">SetTableEntry</a> routine.


### -field MaskTableEntry

A pointer to the interface's <a href="..\wdm\nc-wdm-pci_msix_maskunmask_entry.md">MaskTableEntry</a> routine.


### -field UnmaskTableEntry

A pointer to the interface's <a href="..\wdm\nc-wdm-pci_msix_maskunmask_entry.md">UnmaskTableEntry</a> routine.


### -field GetTableEntry

Reserved for future use.


### -field GetTableSize

Reserved for future use.


## -remarks



A driver obtains a pointer to the <b>PCI_MSIX_TABLE_CONFIG_INTERFACE</b> structure by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> IRP to its bus driver with <b>InterfaceType</b> set to <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff558787">GUID_MSIX_TABLE_CONFIG_INTERFACE</a>.




## -see-also

<a href="..\wdm\nc-wdm-pci_msix_set_entry.md">SetTableEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff558787">GUID_MSIX_TABLE_CONFIG_INTERFACE</a>



<a href="..\wudfwdm\nc-wudfwdm-pinterface_reference.md">InterfaceReference</a>



<a href="..\wudfwdm\nc-wudfwdm-pinterface_dereference.md">InterfaceDereference</a>



<a href="..\wdm\nc-wdm-pci_msix_maskunmask_entry.md">MaskTableEntry</a>



<a href="..\wdm\nc-wdm-pci_msix_maskunmask_entry.md">UnmaskTableEntry</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCI_MSIX_TABLE_CONFIG_INTERFACE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

