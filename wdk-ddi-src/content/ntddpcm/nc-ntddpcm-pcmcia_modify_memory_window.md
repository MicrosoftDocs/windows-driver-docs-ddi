---
UID: NC:ntddpcm.PCMCIA_MODIFY_MEMORY_WINDOW
title: PCMCIA_MODIFY_MEMORY_WINDOW (ntddpcm.h)
description: The PCMCIA_MODIFY_MEMORY_WINDOW interface routine sets the attributes of a memory window for a PCMCIA memory card. The memory window is mapped by the PCMCIA bus driver.
old-location: pcmcia\pcmcia_modify_memory_window.htm
tech.root: PCMCIA
ms.date: 02/15/2018
keywords: ["PCMCIA_MODIFY_MEMORY_WINDOW callback function"]
ms.keywords: ModifyMemoryWindow, ModifyMemoryWindow callback function [Buses], PCMCIA.pcmcia_modify_memory_window, PCMCIA_MODIFY_MEMORY_WINDOW, PCMCIA_MODIFY_MEMORY_WINDOW callback, memcdref_fdb376f2-4f80-4a35-ab23-f007bdc05cad.xml, ntddpcm/ModifyMemoryWindow
req.header: ntddpcm.h
req.include-header: Ntddpcm.h
req.target-type: Desktop
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
req.irql: <=DISPATCH_LEVEL (See Remarks section.)
targetos: Windows
req.typenames: 
f1_keywords:
 - PCMCIA_MODIFY_MEMORY_WINDOW
 - ntddpcm/PCMCIA_MODIFY_MEMORY_WINDOW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ntddpcm.h
api_name:
 - ModifyMemoryWindow
---

# PCMCIA_MODIFY_MEMORY_WINDOW callback function


## -description

The <b>PCMCIA_MODIFY_MEMORY_WINDOW</b> interface routine sets the attributes of a memory window for a PCMCIA memory card. The memory window is mapped by the PCMCIA bus driver.

## -parameters

### -param Context 

[in, optional]
Pointer to the context for the interface routine.

### -param HostBase 

[in]
Specifies the physical memory window to map. <i>HostBase</i> is the base address for the memory card in the system's physical address space.

### -param CardBase 

[in]
Specifies the byte offset in the PC Card's or CardBus card's memory where the memory mapping begins.

### -param Enable 

[in]
Specifies permission to access the memory window. If <i>Enable</i> is <b>TRUE</b>, memory access is permitted, otherwise memory access is not permitted.

### -param WindowSize 

[in, optional]
Specifies the size, in bytes, of the memory window that is mapped. The value of <i>WindowSize</i> cannot exceed the memory window granted to the driver in its assigned resources. If the value of Enable is <b>TRUE</b> and the value of WindowSize is zero, the size of the memory window granted to the driver in its assigned resources is used. If <i>Enable</i> is <b>FALSE</b>, <i>WindowSize</i> is not used.

### -param AccessSpeed 

[in, optional]
Specifies the access speed of the PC Card or CardBus card. The value of <i>AccessSpeed</i> is encoded as specified by the <i>PC Card Standard, Release 6.1</i>. If Enable is <b>FALSE</b>, <i>AccessSpeed</i> is not used.

### -param BusWidth 

[in, optional]
Specifies the width of bus access to the PCMCIA memory card. <i>BusWidth</i> must be one of the following values:





#### PCMCIA_MEMORY_8BIT_ACCESS

If <i>Enable</i> is <b>FALSE</b>, <i>BusWidth</i> is not used.

### -param IsAttributeMemory

#### - AttributeMemory [in, optional]

Must be <b>FALSE</b> for common memory and <b>TRUE</b> for attribute memory.

## -returns

The <b>PCMCIA_MODIFY_MEMORY_WINDOW</b> interface routine returns <b>TRUE</b> if the memory window is successfully enabled or disabled, as specified by the <i>Enable</i> parameter.

## -remarks

A caller must set the <i>Context</i> parameter to the context that is specified by the PCMCIA bus driver. The PCMCIA bus driver returns the context for the interface routines in the <b>Context</b> member of the same PCMCIA_INTERFACE_STANDARD structure that contains the pointers to the interface routines. If the <i>Context</i> parameter is not valid, system behavior is not defined, and the system might halt.

Callers of this routine must be running at IRQL <= DISPATCH_LEVEL. To maintain overall system performance, it is recommended that drivers call this routine at IRQL < DISPATCH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddpcm/nc-ntddpcm-pcmcia_is_write_protected">PCMCIA_IS_WRITE_PROTECTED</a>



<a href="/windows-hardware/drivers/ddi/ntddpcm/nc-ntddpcm-pcmcia_set_vpp">PCMCIA_SET_VPP</a>
