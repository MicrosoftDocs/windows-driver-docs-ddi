---
UID: NS:ntddpcm._PCMCIA_INTERFACE_STANDARD
title: _PCMCIA_INTERFACE_STANDARD (ntddpcm.h)
description: The PCMCIA bus driver makes the PCMCIA_INTERFACE_STANDARD interface available to PCMCIA memory card drivers in order to allow them to make direct calls to the bus driver without allocating IRPs.
old-location: pcmcia\pcmcia_interface_standard.htm
tech.root: PCMCIA
ms.assetid: 3c98fe7b-e60a-4494-b1f0-847a7cbe9d3a
ms.date: 02/15/2018
ms.keywords: "*PPCMCIA_INTERFACE_STANDARD, PCMCIA.pcmcia_interface_standard, PCMCIA_INTERFACE_STANDARD, PCMCIA_INTERFACE_STANDARD structure [Buses], PPCMCIA_INTERFACE_STANDARD, PPCMCIA_INTERFACE_STANDARD structure pointer [Buses], _PCMCIA_INTERFACE_STANDARD, memcdref_768387a3-0148-4f5e-972a-983b7827a634.xml, ntddpcm/PCMCIA_INTERFACE_STANDARD, ntddpcm/PPCMCIA_INTERFACE_STANDARD"
ms.topic: struct
f1_keywords:
 - "ntddpcm/PCMCIA_INTERFACE_STANDARD"
req.header: ntddpcm.h
req.include-header: Ntddpcm.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddpcm.h
api_name:
- PCMCIA_INTERFACE_STANDARD
product:
- Windows
targetos: Windows
req.typenames: PCMCIA_INTERFACE_STANDARD, *PPCMCIA_INTERFACE_STANDARD
---

# _PCMCIA_INTERFACE_STANDARD structure


## -description


The PCMCIA bus driver makes the PCMCIA_INTERFACE_STANDARD interface available to PCMCIA memory card drivers in order to allow them to make direct calls to the bus driver without allocating IRPs. 


## -struct-fields




### -field Size

Indicates the size of the returned interface. 


### -field Version

Indicates the version of the returned interface. 


### -field InterfaceReference

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a> implementation. 


### -field InterfaceDereference

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a> implementation. 


### -field Context

Pointer to an opaque handle that contains interface context information. Drivers that call routines that belong to the <b>PCMCIA_INTERFACE_STANDARD</b> interface must pass this value to the interface routines when they call them. 


### -field ModifyMemoryWindow

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/nc-ntddpcm-pcmcia_modify_memory_window">PCMCIA_MODIFY_MEMORY_WINDOW</a> interface routine. 


### -field SetVpp

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/nc-ntddpcm-pcmcia_set_vpp">PCMCIA_SET_VPP</a> interface routine.


### -field IsWriteProtected

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/nc-ntddpcm-pcmcia_is_write_protected">PCMCIA_IS_WRITE_PROTECTED</a> interface routine.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/nc-ntddpcm-pcmcia_is_write_protected">PCMCIA_IS_WRITE_PROTECTED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/nc-ntddpcm-pcmcia_modify_memory_window">PCMCIA_MODIFY_MEMORY_WINDOW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/nc-ntddpcm-pcmcia_set_vpp">PCMCIA_SET_VPP</a>
 

 

