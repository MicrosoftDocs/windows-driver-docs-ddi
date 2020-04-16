---
UID: NC:ntddpcm.PCMCIA_SET_VPP
title: PCMCIA_SET_VPP (ntddpcm.h)
description: The PCMCIA_SET_VPP interface routine sets the power level of the Vpp PCMCIA pin (secondary power source).
old-location: pcmcia\pcmcia_set_vpp.htm
tech.root: PCMCIA
ms.assetid: 63c34784-6ea5-49e5-8ee7-79b70e5137f7
ms.date: 02/15/2018
keywords: ["PCMCIA_SET_VPP callback function"]
ms.keywords: PCMCIA.pcmcia_set_vpp, PCMCIA_SET_VPP, PCMCIA_SET_VPP callback, SetVpp, SetVpp callback function [Buses], memcdref_fe05cf85-9e4b-4267-9214-b8809e42cd5a.xml, ntddpcm/SetVpp
f1_keywords:
 - "ntddpcm/SetVpp"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ntddpcm.h
api_name:
- SetVpp
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCMCIA_SET_VPP callback function


## -description


The <b>PCMCIA_SET_VPP</b> interface routine sets the power level of the Vpp PCMCIA pin (secondary power source).


## -parameters




### -param Context [in, optional]

Pointer to the context for the interface routine.


### -param VppLevel [in]

Specifies the voltage level to set on the Vpp pin. <i>VppLevel</i> must be one of the following values:





#### PCMCIA_VPP_0V

Specifies that the voltage on the Vpp pin be set to zero volts and that the Vpp pin be disabled.



#### PCMCIA_VPP_12V

Specifies that the voltage on the Vpp pin be set to twelve volts.



#### PCMCIA_VPP_IS_VCC

Specifies that the voltage on the Vpp pin be set to equal the voltage on the Vcc (primary card power) pin.


## -returns



The <b>PCMCIA_SET_VPP</b> interface routine returns <b>TRUE</b> after the requested voltage level is set.




## -remarks



The <b>PCMCIA_SET_VPP</b> interface routine returns control to the caller after the requested voltage is established in a stable state for the card.

A caller must set the <i>Context</i> parameter to the context that is specified by the PCMCIA bus driver. The PCMCIA bus driver returns the context for the interface routines in the <b>Context</b> member of the same PCMCIA_INTERFACE_STANDARD structure that contains the pointers to the interface routines. If the <i>Context</i> parameter is not valid, system behavior is not defined, and the system might halt.

Callers of this routine can run at IRQL <= DISPATCH_LEVEL. To maintain overall system performance, it is recommended that drivers call this routine at IRQL < DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/nc-ntddpcm-pcmcia_is_write_protected">PCMCIA_IS_WRITE_PROTECTED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/nc-ntddpcm-pcmcia_modify_memory_window">PCMCIA_MODIFY_MEMORY_WINDOW</a>
 

 

