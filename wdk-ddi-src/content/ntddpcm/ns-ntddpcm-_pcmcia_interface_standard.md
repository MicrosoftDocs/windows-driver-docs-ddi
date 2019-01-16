---
UID: NS:ntddpcm._PCMCIA_INTERFACE_STANDARD
title: "_PCMCIA_INTERFACE_STANDARD"
description: The PCMCIA bus driver makes the PCMCIA_INTERFACE_STANDARD interface available to PCMCIA memory card drivers in order to allow them to make direct calls to the bus driver without allocating IRPs.
old-location: pcmcia\pcmcia_interface_standard.htm
tech.root: PCMCIA
ms.assetid: 3c98fe7b-e60a-4494-b1f0-847a7cbe9d3a
ms.date: 02/15/2018
ms.keywords: "*PPCMCIA_INTERFACE_STANDARD, PCMCIA.pcmcia_interface_standard, PCMCIA_INTERFACE_STANDARD, PCMCIA_INTERFACE_STANDARD structure [Buses], PPCMCIA_INTERFACE_STANDARD, PPCMCIA_INTERFACE_STANDARD structure pointer [Buses], _PCMCIA_INTERFACE_STANDARD, memcdref_768387a3-0148-4f5e-972a-983b7827a634.xml, ntddpcm/PCMCIA_INTERFACE_STANDARD, ntddpcm/PPCMCIA_INTERFACE_STANDARD"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddpcm.h
api_name:
-	PCMCIA_INTERFACE_STANDARD
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

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547833">InterfaceReference</a> implementation. 


### -field InterfaceDereference

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a> implementation. 


### -field Context

Pointer to an opaque handle that contains interface context information. Drivers that call routines that belong to the <b>PCMCIA_INTERFACE_STANDARD</b> interface must pass this value to the interface routines when they call them. 


### -field ModifyMemoryWindow

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537610">PCMCIA_MODIFY_MEMORY_WINDOW</a> interface routine. 


### -field SetVpp

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537611">PCMCIA_SET_VPP</a> interface routine.


### -field IsWriteProtected

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537609">PCMCIA_IS_WRITE_PROTECTED</a> interface routine.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537609">PCMCIA_IS_WRITE_PROTECTED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537610">PCMCIA_MODIFY_MEMORY_WINDOW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537611">PCMCIA_SET_VPP</a>
 

 

