---
UID: NC:wdm.ENABLE_VIRTUALIZATION
title: ENABLE_VIRTUALIZATION (wdm.h)
description: The EnableVirtualization routine enables or disables virtualization for a PCI Express (PCIe) device that supports the single root I/O virtualization (SR-IOV) interface.
old-location: pci\enablevirtualization.htm
tech.root: PCI
ms.assetid: BC833231-CA7B-4E68-9498-46F1D4B32B88
ms.date: 02/24/2018
keywords: ["ENABLE_VIRTUALIZATION callback"]
ms.keywords: ENABLE_VIRTUALIZATION, EnableVirtualization, EnableVirtualization routine, PCI.enablevirtualization, wdm/EnableVirtualization
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2012 and later versions of Windows.
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
f1_keywords:
 - ENABLE_VIRTUALIZATION
 - wdm/ENABLE_VIRTUALIZATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - EnableVirtualization
---

# ENABLE_VIRTUALIZATION callback


## -description

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-enable_virtualization">EnableVirtualization</a> routine enables or disables virtualization for a PCI Express (PCIe) device that supports the single root I/O virtualization (SR-IOV) interface.

## -parameters

### -param Context 

[in, out]
A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh406642(v=vs.85)">PCI_VIRTUALIZATION_INTERFACE</a> structure for the interface.

### -param NumVFs 

[in]
The number of PCIe virtual functions (VFs) that are to be enabled for the device. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-enable_virtualization">EnableVirtualization</a> routine sets the <b>NumVFs</b> member of the PCIe SR-IOV Extended Capability structure to the value of the <i>NumVFs</i> parameter.



<div class="alert"><b>Note</b>  If the <i>EnableVirtualization</i> parameter is <b>FALSE</b>, the <i>NumVFs</i> parameter must be set to zero.

</div>
<div> </div>

### -param EnableVfMigration 

[in]
A BOOLEAN value that indicates whether the multi-root I/O virtualization (MR-IOV) base function (BF) can dynamically reprovision the PCIe physical function (PF) of the device   as a VF at run time.

<div class="alert"><b>Note</b>  This parameter is only applicable to devices that support both the SR-IOV and MR-IOV interfaces. The driver must set this parameter to <b>FALSE</b> if the device supports only the SR-IOV interface and not the MR-IOV interface.</div>
<div> </div>

### -param EnableMigrationInterrupt 

[in]
A BOOLEAN value that indicates whether the interrupt associated with the PF should be masked or unmasked during VF migration.

<div class="alert"><b>Note</b>  If the <i>EnableVfMigration</i> parameters is <b>FALSE</b>, the driver must also set this parameter to <b>FALSE</b>.</div>
<div> </div>

### -param EnableVirtualization 

[in]
A BOOLEAN value that indicates whether virtualization is enabled on the PCIe configuration space of the device. If the <i>EnableVirtualization</i> parameter is <b>TRUE</b>, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-enable_virtualization">EnableVirtualization</a> routine sets the VF Enable bit of the PCIe SR-IOV Control field. The <i>EnableVirtualization</i> routine clears this bit if the <i>EnableVirtualization</i> parameter is <b>FALSE</b>.

## -returns

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-enable_virtualization">EnableVirtualization</a> routine returns one of the following NTSTATUS values:

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
The <i>NumVFs</i> parameter is either zero or  is larger than the value of the <b>TotalVFs</b> member of the SR-IOV Extended Capability structure for the device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
Virtualization is already enabled on the device and the <i>EnableVirtualization</i> parameter is <b>TRUE</b>, or virtualization is already disabled on the device and the <i>EnableVirtualization</i> parameter is <b>FALSE</b>.

</td>
</tr>
</table>

## -prototype

```cpp
ENABLE_VIRTUALIZATION EnableVirtualization;

NTSTATUS EnableVirtualization(
  _Inout_ PVOID   Context,
  _In_    UINT16  NumVFs,
  _In_    BOOLEAN EnableVfMigration,
  _In_    BOOLEAN EnableMigrationInterrupt,
  _In_    BOOLEAN EnableVirtualization
)
{ ... }
```

## -remarks

Drivers call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-enable_virtualization">EnableVirtualization</a> routine to configure the SR-IOV Extended Capability fields in the PCIe configuration space. This call enables or disables virtualization in the configuration space, and specifies the number of VFs that should be exposed to the PCIe fabric by the device.



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-enable_virtualization">EnableVirtualization</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh406642(v=vs.85)">PCI_VIRTUALIZATION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>



<b></b>

