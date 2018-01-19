---
UID: NS:pepfx._PEP_UNMASKED_INTERRUPT_FLAGS
title: _PEP_UNMASKED_INTERRUPT_FLAGS
author: windows-driver-content
description: The PEP_UNMASKED_INTERRUPT_FLAGS union indicates whether an unmasked interrupt source is a primary interrupt or a secondary interrupt.
old-location: kernel\pep_unmasked_interrupt_flags.htm
old-project: kernel
ms.assetid: A385FBF9-2222-49E0-A708-1638C0D2FF7A
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _PEP_UNMASKED_INTERRUPT_FLAGS, PEP_UNMASKED_INTERRUPT_FLAGS, *PPEP_UNMASKED_INTERRUPT_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_UNMASKED_INTERRUPT_FLAGS
req.alt-loc: pepfx.h
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
req.typenames: PEP_UNMASKED_INTERRUPT_FLAGS, *PPEP_UNMASKED_INTERRUPT_FLAGS
---

# _PEP_UNMASKED_INTERRUPT_FLAGS structure



## -description
The <b>PEP_UNMASKED_INTERRUPT_FLAGS</b> union indicates whether an unmasked interrupt source is a primary interrupt or a secondary interrupt.



## -syntax

````
typedef union _PEP_UNMASKED_INTERRUPT_FLAGS {
  struct {
    USHORT SecondaryInterrupt  :1;
    USHORT Reserved  :15;
  };
  USHORT AsUSHORT;
} PEP_UNMASKED_INTERRUPT_FLAGS;
````


## -struct-fields

### -field ( unnamed struct )

A structure that contains the bitfields for the individual unmasked interrupt flags.


### -field SecondaryInterrupt

Whether this interrupt is a primary interrupt or a secondary interrupt. This bitfield is 0 if the interrupt source is a primary interrupt, and is 1 is the interrupt source is a secondary interrupt. For more information, see <a href="https://msdn.microsoft.com/731B0E36-4480-4B69-931E-1F7B40B18911">Primary and Secondary Interrupts</a>.


### -field Reserved

Reserved for future use.

</dd>
</dl>

### -field AsUSHORT

A USHORT value that contains all of the unmasked interrupt flags.


## -remarks
The <b>Flags</b> member of the <a href="..\pepfx\ns-pepfx-_pep_unmasked_interrupt_information.md">PEP_UNMASKED_INTERRUPT_INFORMATION</a> structure is a <b>PEP_UNMASKED_INTERRUPT_FLAGS</b> union.


## -see-also
<dl>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_unmasked_interrupt_information.md">PEP_UNMASKED_INTERRUPT_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_UNMASKED_INTERRUPT_FLAGS union%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

