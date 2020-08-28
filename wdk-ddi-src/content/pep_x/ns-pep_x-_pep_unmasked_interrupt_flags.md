---
UID: NS:pep_x._PEP_UNMASKED_INTERRUPT_FLAGS
title: _PEP_UNMASKED_INTERRUPT_FLAGS (pep_x.h)
description: The PEP_UNMASKED_INTERRUPT_FLAGS union indicates whether an unmasked interrupt source is a primary interrupt or a secondary interrupt.
old-location: kernel\pep_unmasked_interrupt_flags.htm
tech.root: kernel
ms.assetid: A385FBF9-2222-49E0-A708-1638C0D2FF7A
ms.date: 04/30/2018
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
 - PEP_UNMASKED_INTERRUPT_FLAGS
---

# _PEP_UNMASKED_INTERRUPT_FLAGS structure


## -description

The <b>PEP_UNMASKED_INTERRUPT_FLAGS</b> union indicates whether an unmasked interrupt source is a primary interrupt or a secondary interrupt.

## -struct-fields

### -field SecondaryInterrupt

### -field Reserved

### -field AsUSHORT

A USHORT value that contains all of the unmasked interrupt flags.


#### - ( unnamed struct )

A structure that contains the bitfields for the individual unmasked interrupt flags.



#### SecondaryInterrupt

Whether this interrupt is a primary interrupt or a secondary interrupt. This bitfield is 0 if the interrupt source is a primary interrupt, and is 1 is the interrupt source is a secondary interrupt. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/primary-and-secondary-interrupts">Primary and Secondary Interrupts</a>.



#### Reserved

Reserved for future use.


##### - ( unnamed struct ).Reserved

Reserved for future use.


##### - ( unnamed struct ).SecondaryInterrupt

Whether this interrupt is a primary interrupt or a secondary interrupt. This bitfield is 0 if the interrupt source is a primary interrupt, and is 1 is the interrupt source is a secondary interrupt. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/primary-and-secondary-interrupts">Primary and Secondary Interrupts</a>.

## -remarks

The <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_unmasked_interrupt_information">PEP_UNMASKED_INTERRUPT_INFORMATION</a> structure is a <b>PEP_UNMASKED_INTERRUPT_FLAGS</b> union.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_unmasked_interrupt_information">PEP_UNMASKED_INTERRUPT_INFORMATION</a>

