---
UID: NS:wdm._PCI_MSIX_TABLE_CONFIG_INTERFACE
title: "_PCI_MSIX_TABLE_CONFIG_INTERFACE"
author: windows-driver-content
description: The PCI_MSIX_TABLE_CONFIG_INTERFACE structure enables device drivers to modify their MSI-X interrupt settings. This structure describes the GUID_MSIX_TABLE_CONFIG_INTERFACE interface.
old-location: kernel\pci_msix_table_config_interface.htm
old-project: kernel
ms.assetid: 0809a963-a0e7-49ca-b483-c39f1606051e
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PPCI_MSIX_TABLE_CONFIG_INTERFACE, PCI_MSIX_TABLE_CONFIG_INTERFACE, PCI_MSIX_TABLE_CONFIG_INTERFACE structure [Kernel-Mode Driver Architecture], PPCI_MSIX_TABLE_CONFIG_INTERFACE, PPCI_MSIX_TABLE_CONFIG_INTERFACE structure pointer [Kernel-Mode Driver Architecture], _PCI_MSIX_TABLE_CONFIG_INTERFACE, drvr_interface_86de1cfb-1eac-442b-a154-6f23fcab87cd.xml, kernel.pci_msix_table_config_interface, wdm/PCI_MSIX_TABLE_CONFIG_INTERFACE, wdm/PPCI_MSIX_TABLE_CONFIG_INTERFACE"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	PCI_MSIX_TABLE_CONFIG_INTERFACE
product: Windows
targetos: Windows
req.typenames: PCI_MSIX_TABLE_CONFIG_INTERFACE, *PPCI_MSIX_TABLE_CONFIG_INTERFACE
---

# _PCI_MSIX_TABLE_CONFIG_INTERFACE structure


## -description


The <b>PCI_MSIX_TABLE_CONFIG_INTERFACE</b> structure enables device drivers to modify their MSI-X interrupt settings. This structure  describes the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff558787">GUID_MSIX_TABLE_CONFIG_INTERFACE</a> interface.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The driver-defined interface version.


### -field Context

A pointer to interface-specific context information. 


### -field InterfaceReference

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547833">InterfaceReference</a> routine that increments the interface's reference count.


### -field InterfaceDereference

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a> routine that decrements the interface's reference count.


### -field SetTableEntry

A pointer to the interface's <a href="https://msdn.microsoft.com/library/windows/hardware/gg604857">SetTableEntry</a> routine.


### -field MaskTableEntry

A pointer to the interface's <a href="https://msdn.microsoft.com/library/windows/hardware/gg604852">MaskTableEntry</a> routine.


### -field UnmaskTableEntry

A pointer to the interface's <a href="https://msdn.microsoft.com/library/windows/hardware/gg604859">UnmaskTableEntry</a> routine.


### -field GetTableEntry

Reserved for future use.


### -field GetTableSize

Reserved for future use.


## -remarks



A driver obtains a pointer to the <b>PCI_MSIX_TABLE_CONFIG_INTERFACE</b> structure by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> IRP to its bus driver with <b>InterfaceType</b> set to <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff558787">GUID_MSIX_TABLE_CONFIG_INTERFACE</a>.




## -see-also




<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff558787">GUID_MSIX_TABLE_CONFIG_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547833">InterfaceReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/gg604852">MaskTableEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/gg604857">SetTableEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/gg604859">UnmaskTableEntry</a>
 

 

