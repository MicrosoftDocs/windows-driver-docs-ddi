---
UID: NC:wdm.PCI_MSIX_MASKUNMASK_ENTRY
title: PCI_MSIX_MASKUNMASK_ENTRY (wdm.h)
description: The MaskTableEntry routine masks an interrupt in the MSI-X hardware interrupt table.
old-location: kernel\masktableentry.htm
tech.root: kernel
ms.assetid: ADD9AA38-594D-413A-BE8B-BCC6B62EAA8E
ms.date: 04/30/2018
ms.keywords: MaskTableEntry, MaskTableEntry routine [Kernel-Mode Driver Architecture], PCI_MSIX_MASKUNMASK_ENTRY, drvr_interface_c4246cdd-8a44-423e-b145-fae6e1e96716.xml, kernel.masktableentry, kernel.msixmasktableentry, wdm/MaskTableEntry
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.irql: "<= DIRQL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- MaskTableEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCI_MSIX_MASKUNMASK_ENTRY callback function


## -description


The <i>MaskTableEntry</i> routine masks an interrupt in the MSI-X hardware interrupt table.


## -parameters




### -param Context [in]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_pci_msix_table_config_interface">PCI_MSIX_TABLE_CONFIG_INTERFACE</a> structure for the interface.


### -param TableEntry [in]

The index of the table entry in the MSI-X hardware interrupt table.


## -returns



The <i>MaskTableEntry</i> routine might return one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>TableEntry</i> parameter is invalid.

</td>
</tr>
</table>
 




## -remarks



If a table entry is masked, the device does not generate any interrupts that correspond to that table entry.

You can unmask the table entry by calling <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/gg604859(v=vs.85)">UnmaskTableEntry</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_pci_msix_table_config_interface">PCI_MSIX_TABLE_CONFIG_INTERFACE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/gg604859(v=vs.85)">UnmaskTableEntry</a>
 

 

