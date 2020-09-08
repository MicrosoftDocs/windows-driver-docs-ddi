---
UID: NC:ntddpcm.PCMCIA_IS_WRITE_PROTECTED
title: PCMCIA_IS_WRITE_PROTECTED (ntddpcm.h)
description: The PCMCIA_IS_WRITE_PROTECTED interface routine returns the write-protect condition of a PCMCIA memory card.
old-location: pcmcia\pcmcia_is_write_protected.htm
tech.root: PCMCIA
ms.assetid: d270f39a-d8e8-4ec6-987e-e755da767495
ms.date: 02/15/2018
keywords: ["PCMCIA_IS_WRITE_PROTECTED callback function"]
ms.keywords: IsWriteProtected, IsWriteProtected callback function [Buses], PCMCIA.pcmcia_is_write_protected, PCMCIA_IS_WRITE_PROTECTED, PCMCIA_IS_WRITE_PROTECTED callback, memcdref_e7dab6ad-c94a-42c9-a969-f102c58e4d3c.xml, ntddpcm/IsWriteProtected
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
 - PCMCIA_IS_WRITE_PROTECTED
 - ntddpcm/PCMCIA_IS_WRITE_PROTECTED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ntddpcm.h
api_name:
 - IsWriteProtected
---

# PCMCIA_IS_WRITE_PROTECTED callback function


## -description

The <b>PCMCIA_IS_WRITE_PROTECTED</b> interface routine returns the write-protect condition of a PCMCIA memory card.

## -parameters

### -param Context 

[in, optional]
Pointer to the context for the interface routine.

## -returns

The <b>PCMCIA_IS_WRITE_PROTECTED </b>interface routine returns <b>TRUE</b> if the memory card is write-protected, otherwise it returns <b>FALSE</b>.

## -remarks

A caller must set the <i>Context</i> parameter to the context that is specified by the PCMCIA bus driver. The PCMCIA bus driver returns the context for the interface routines in the <b>Context</b> member of the same PCMCIA_INTERFACE_STANDARD structure that contains the pointers to the interface routines. If the <i>Context</i> parameter is not valid, system behavior is not defined, and the system might halt.

Callers of this routine must be running at IRQL <= DISPATCH_LEVEL. To maintain overall system performance, it is recommended that drivers call this routine at IRQL < DISPATCH_LEVEL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/nc-ntddpcm-pcmcia_modify_memory_window">PCMCIA_MODIFY_MEMORY_WINDOW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/nc-ntddpcm-pcmcia_set_vpp">PCMCIA_SET_VPP</a>

