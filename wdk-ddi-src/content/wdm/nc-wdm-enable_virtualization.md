---
UID: NC:wdm.ENABLE_VIRTUALIZATION
title: ENABLE_VIRTUALIZATION
author: windows-driver-content
description: The EnableVirtualization routine enables or disables virtualization for a PCI Express (PCIe) device that supports the single root I/O virtualization (SR-IOV) interface.
old-location: pci\enablevirtualization.htm
old-project: PCI
ms.assetid: BC833231-CA7B-4E68-9498-46F1D4B32B88
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PCI.enablevirtualization, EnableVirtualization routine, EnableVirtualization, ENABLE_VIRTUALIZATION, ENABLE_VIRTUALIZATION, wdm/EnableVirtualization
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	EnableVirtualization
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# ENABLE_VIRTUALIZATION callback


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451005">EnableVirtualization</a> routine enables or disables virtualization for a PCI Express (PCIe) device that supports the single root I/O virtualization (SR-IOV) interface.


## -prototype


````
ENABLE_VIRTUALIZATION EnableVirtualization;

NTSTATUS EnableVirtualization(
  _Inout_ PVOID   Context,
  _In_    UINT16  NumVFs,
  _In_    BOOLEAN EnableVfMigration,
  _In_    BOOLEAN EnableMigrationInterrupt,
  _In_    BOOLEAN EnableVirtualization
)
{ ... }
````


## -parameters




### -param Context [in, out]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a> structure for the interface.


### -param NumVFs [in]

The number of PCIe virtual functions (VFs) that are to be enabled for the device. The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451005">EnableVirtualization</a> routine sets the <b>NumVFs</b> member of the PCIe SR-IOV Extended Capability structure to the value of the <i>NumVFs</i> parameter. 



<div class="alert"><b>Note</b>  If the <i>EnableVirtualization</i> parameter is <b>FALSE</b>, the <i>NumVFs</i> parameter must be set to zero.

</div>
<div> </div>

### -param EnableVfMigration [in]

A BOOLEAN value that indicates whether the multi-root I/O virtualization (MR-IOV) base function (BF) can dynamically reprovision the PCIe physical function (PF) of the device   as a VF at run time.

<div class="alert"><b>Note</b>  This parameter is only applicable to devices that support both the SR-IOV and MR-IOV interfaces. The driver must set this parameter to <b>FALSE</b> if the device supports only the SR-IOV interface and not the MR-IOV interface.</div>
<div> </div>

### -param EnableMigrationInterrupt [in]

A BOOLEAN value that indicates whether the interrupt associated with the PF should be masked or unmasked during VF migration.

<div class="alert"><b>Note</b>  If the <i>EnableVfMigration</i> parameters is <b>FALSE</b>, the driver must also set this parameter to <b>FALSE</b>.</div>
<div> </div>

### -param EnableVirtualization [in]

A BOOLEAN value that indicates whether virtualization is enabled on the PCIe configuration space of the device. If the <i>EnableVirtualization</i> parameter is <b>TRUE</b>, the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451005">EnableVirtualization</a> routine sets the VF Enable bit of the PCIe SR-IOV Control field. The <i>EnableVirtualization</i> routine clears this bit if the <i>EnableVirtualization</i> parameter is <b>FALSE</b>.




## -returns



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451005">EnableVirtualization</a> routine returns one of the following NTSTATUS values:

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
 




## -remarks



Drivers call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451005">EnableVirtualization</a> routine to configure the SR-IOV Extended Capability fields in the PCIe configuration space. This call enables or disables virtualization in the configuration space, and specifies the number of VFs that should be exposed to the PCIe fabric by the device.



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451005">EnableVirtualization</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\pci]:%20ENABLE_VIRTUALIZATION routine%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

