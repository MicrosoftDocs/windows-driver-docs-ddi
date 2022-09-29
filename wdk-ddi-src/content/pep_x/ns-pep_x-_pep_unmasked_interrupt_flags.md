---
UID: NS:pep_x._PEP_UNMASKED_INTERRUPT_FLAGS
title: _PEP_UNMASKED_INTERRUPT_FLAGS (pep_x.h)
description: Learn how the PEP_UNMASKED_INTERRUPT_FLAGS union indicates whether an unmasked interrupt source is a primary interrupt or a secondary interrupt.
old-location: kernel\pep_unmasked_interrupt_flags.htm
tech.root: kernel
ms.date: 08/09/2022
keywords: ["PEP_UNMASKED_INTERRUPT_FLAGS structure"]
ms.keywords: "*PPEP_UNMASKED_INTERRUPT_FLAGS, PEP_UNMASKED_INTERRUPT_FLAGS, PEP_UNMASKED_INTERRUPT_FLAGS union [Kernel-Mode Driver Architecture], _PEP_UNMASKED_INTERRUPT_FLAGS, kernel.pep_unmasked_interrupt_flags, pepfx/PEP_UNMASKED_INTERRUPT_FLAGS"
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
targetos: Windows
req.typenames: PEP_UNMASKED_INTERRUPT_FLAGS, *PPEP_UNMASKED_INTERRUPT_FLAGS
f1_keywords:
 - _PEP_UNMASKED_INTERRUPT_FLAGS
 - pep_x/_PEP_UNMASKED_INTERRUPT_FLAGS
 - PPEP_UNMASKED_INTERRUPT_FLAGS
 - pep_x/PPEP_UNMASKED_INTERRUPT_FLAGS
 - PEP_UNMASKED_INTERRUPT_FLAGS
 - pep_x/PEP_UNMASKED_INTERRUPT_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_UNMASKED_INTERRUPT_FLAGS
 - PPEP_UNMASKED_INTERRUPT_FLAGS
 - PEP_UNMASKED_INTERRUPT_FLAGS
---

# _PEP_UNMASKED_INTERRUPT_FLAGS union (pep_x.h)

## -description

The **PEP_UNMASKED_INTERRUPT_FLAGS** union indicates whether an unmasked interrupt source is a primary interrupt or a secondary interrupt.

## -struct-fields

### -field SecondaryInterrupt

Whether this interrupt is a primary interrupt or a secondary interrupt. This bit field is 0 if the interrupt source is a primary interrupt, and is 1 is the interrupt source is a secondary interrupt. For more information, see [Primary and Secondary Interrupts](/windows-hardware/drivers/gpio/primary-and-secondary-interrupts).

### -field Reserved

Reserved for future use.

### -field AsUSHORT

A USHORT value that contains all of the unmasked interrupt flags.

Whether this interrupt is a primary interrupt or a secondary interrupt. This bit field is 0 if the interrupt source is a primary interrupt, and is 1 is the interrupt source is a secondary interrupt. For more information, see [Primary and Secondary Interrupts](/windows-hardware/drivers/gpio/primary-and-secondary-interrupts).

## -remarks

The unnamed struct contains the bit fields for the individual unmasked interrupt flags.

The *Flags* member of the [ns-pep_x-_pep_work_information.md](../pepfx/ns-pepfx-_pep_unmasked_interrupt_information.md) structure is a **PEP_UNMASKED_INTERRUPT_FLAGS** union.

## -see-also

- [PEP_UNMASKED_INTERRUPT_INFORMATION](../pepfx/ns-pepfx-_pep_unmasked_interrupt_information.md)
