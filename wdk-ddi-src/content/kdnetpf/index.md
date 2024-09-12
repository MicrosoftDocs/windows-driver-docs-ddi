---
UID: NA:kdnetpf
description: "KDNETPF transport support APIs in the kdnetpf.h header"
title: kdnetpf.h header
ms.topic: reference
tech.root: debugger
ms.date: 08/21/2023
f1_keywords:
 - kdnetpf
 - kdnetpf/kdnetpf
api_name:
 - engextcpp
dev_langs:
 - c++
---

# kdnetpf.h header

## -description

This header is used by miniport NDIS drivers for 2PF debugger support to allow increased performance for high speed network adapters. This feature is available in Windows 11 and later.

Using the PCI multiple Physical Function (PF) feature for KDNET allows for debugging to be enabled with minimal performance impact.

The Physical Function (PF) is a PCI Express (PCIe) function of a network adapter that supports the single root I/O virtualization (SR-IOV) interface. The PF includes the SR-IOV Extended Capability in the PCIe Configuration space. The capability is used to configure and manage the SR-IOV functionality of the network adapter, such as enabling virtualization and exposing PCIe Virtual Functions (VFs).

The PF supports the SR-IOV Extended Capability structure in its PCIe configuration space. This structure is defined in the PCI-SIG Single Root I/O Virtualization and Sharing 1.1 specification.

For more information, see the following topics:

- [Debugger 2PF KDNET Support](/windows-hardware/drivers/network/debugger-2pf-kdnet-support)
- [Debugger APIs](../_debugger/index.md)
