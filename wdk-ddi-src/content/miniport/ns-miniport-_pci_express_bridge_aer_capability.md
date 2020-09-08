---
UID: NS:miniport._PCI_EXPRESS_BRIDGE_AER_CAPABILITY
title: _PCI_EXPRESS_BRIDGE_AER_CAPABILITY (miniport.h)
description: The PCI_EXPRESS_BRIDGE_AER_CAPABILITY structure describes a PCI Express (PCIe) advanced error reporting capability structure for a PCIe bridge device.
old-location: pci\pci_express_bridge_aer_capability.htm
tech.root: PCI
ms.assetid: 06bbd3b8-b917-44ed-880e-9d071146e859
ms.date: 02/24/2018
keywords: ["PCI_EXPRESS_BRIDGE_AER_CAPABILITY structure"]
ms.keywords: "*PPCI_EXPRESS_BRIDGE_AER_CAPABILITY, PCI.pci_express_bridge_aer_capability, PCI_EXPRESS_BRIDGE_AER_CAPABILITY, PCI_EXPRESS_BRIDGE_AER_CAPABILITY structure [Buses], PPCI_EXPRESS_BRIDGE_AER_CAPABILITY, PPCI_EXPRESS_BRIDGE_AER_CAPABILITY structure pointer [Buses], _PCI_EXPRESS_BRIDGE_AER_CAPABILITY, pci_struct_ccc11a2c-4380-44b4-8404-d7d9931887b6.xml, wdm/PCI_EXPRESS_BRIDGE_AER_CAPABILITY, wdm/PPCI_EXPRESS_BRIDGE_AER_CAPABILITY"
req.header: miniport.h
req.include-header: Ntddk.h, Wdm.h, Miniport.h
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
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: PCI_EXPRESS_BRIDGE_AER_CAPABILITY, *PPCI_EXPRESS_BRIDGE_AER_CAPABILITY
f1_keywords:
 - _PCI_EXPRESS_BRIDGE_AER_CAPABILITY
 - miniport/_PCI_EXPRESS_BRIDGE_AER_CAPABILITY
 - PPCI_EXPRESS_BRIDGE_AER_CAPABILITY
 - miniport/PPCI_EXPRESS_BRIDGE_AER_CAPABILITY
 - PCI_EXPRESS_BRIDGE_AER_CAPABILITY
 - miniport/PCI_EXPRESS_BRIDGE_AER_CAPABILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PCI_EXPRESS_BRIDGE_AER_CAPABILITY
---

# _PCI_EXPRESS_BRIDGE_AER_CAPABILITY structure (miniport.h)


## -description

The PCI_EXPRESS_BRIDGE_AER_CAPABILITY structure describes a PCI Express (PCIe) advanced error reporting capability structure for a PCIe bridge device.

## -struct-fields

### -field Header

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_enhanced_capability_header">PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER</a> structure that describes the header for this structure.

### -field UncorrectableErrorStatus

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_uncorrectable_error_status">PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS</a> structure that describes the PCIe uncorrectable error status register of the PCIe AER capability structure.

### -field UncorrectableErrorMask

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_uncorrectable_error_mask">PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK</a> structure that describes the PCIe uncorrectable error mask register of the PCIe AER capability structure.

### -field UncorrectableErrorSeverity

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_uncorrectable_error_severity">PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY</a> structure that describes the PCIe uncorrectable error severity register of the PCIe AER capability structure.

### -field CorrectableErrorStatus

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_uncorrectable_error_status">PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS</a> structure that describes the PCIe uncorrectable error status register of the PCIe AER capability structure.

### -field CorrectableErrorMask

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_uncorrectable_error_mask">PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK</a> structure that describes the PCIe uncorrectable error mask register of the PCIe AER capability structure.

### -field CapabilitiesAndControl

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capabilities">PCI_EXPRESS_AER_CAPABILITIES</a> structure that describes the PCIe advanced error capabilities and control register of the PCIe AER capability structure.

### -field HeaderLog

An array of four 32-bit values that together contain the header for the transaction layer packet (TLP) that corresponds to a detected error.

<div class="alert"><b>Note</b>    Within each 32-bit value in the array, the bytes of the TLP are in big-endian byte order.</div>
<div> </div>

### -field SecUncorrectableErrorStatus

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_sec_uncorrectable_error_status">PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS</a> structure that describes the PCIe secondary uncorrectable error status register of the PCIe AER capability structure.

### -field SecUncorrectableErrorMask

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_sec_uncorrectable_error_mask">PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK</a> structure that describes the PCIe secondary uncorrectable error mask register of the PCIe AER capability structure.

### -field SecUncorrectableErrorSeverity

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_sec_uncorrectable_error_severity">PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY</a> structure that describes the PCIe secondary uncorrectable error severity register of the PCIe AER capability structure.

### -field SecCapabilitiesAndControl

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_sec_aer_capabilities">PCI_EXPRESS_SEC_AER_CAPABILITIES</a> structure that describes the PCIe secondary error capabilities and control register of the PCIe AER capability structure.

### -field SecHeaderLog

An array of four 32-bit values that together contain the header for the transaction on the secondary interface that generated an error.

## -syntax

```cpp
typedef struct _PCI_EXPRESS_BRIDGE_AER_CAPABILITY {
  PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER       Header;
  PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS       UncorrectableErrorStatus;
  PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK         UncorrectableErrorMask;
  PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY     UncorrectableErrorSeverity;
  PCI_EXPRESS_CORRECTABLE_ERROR_STATUS         CorrectableErrorStatus;
  PCI_EXPRESS_CORRECTABLE_ERROR_MASK           CorrectableErrorMask;
  PCI_EXPRESS_AER_CAPABILITIES                 CapabilitiesAndControl;
  ULONG                                        HeaderLog[4];
  PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS   SecUncorrectableErrorStatus;
  PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK     SecUncorrectableErrorMask;
  PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY SecUncorrectableErrorSeverity;
  PCI_EXPRESS_SEC_AER_CAPABILITIES             SecCapabilitiesAndControl;
  ULONG                                        SecHeaderLog[4];
} PCI_EXPRESS_BRIDGE_AER_CAPABILITY, *PPCI_EXPRESS_BRIDGE_AER_CAPABILITY;
```

## -remarks

The PCI_EXPRESS_BRIDGE_AER_CAPABILITY structure is available in Windows Server 2008 and later versions of Windows.

Root ports and root complex event collectors use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structure instead of the PCI_EXPRESS_BRIDGE_AER_CAPABILITY structure to describe the PCIe advanced error reporting capability structure.

All other PCIe devices and ports that are not bridge devices use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability">PCI_EXPRESS_AER_CAPABILITY</a> structure instead of the PCI_EXPRESS_BRIDGE_AER_CAPABILITY structure to describe the PCIe advanced error reporting capability structure.

For additional information about the PCIe advanced error reporting capability structure for PCIe bridge devices, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=69486">PCI Express Bridge Specification</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_sec_uncorrectable_error_status">PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_correctable_error_status">PCI_EXPRESS_CORRECTABLE_ERROR_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_uncorrectable_error_severity">PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_sec_uncorrectable_error_severity">PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_sec_aer_capabilities">PCI_EXPRESS_SEC_AER_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_uncorrectable_error_mask">PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability">PCI_EXPRESS_AER_CAPABILITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capabilities">PCI_EXPRESS_AER_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_enhanced_capability_header">PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_uncorrectable_error_status">PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_sec_uncorrectable_error_mask">PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_correctable_error_mask">PCI_EXPRESS_CORRECTABLE_ERROR_MASK</a>

