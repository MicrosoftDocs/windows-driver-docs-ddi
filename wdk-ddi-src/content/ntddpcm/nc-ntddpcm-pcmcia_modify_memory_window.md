---
UID: NC:ntddpcm.PCMCIA_MODIFY_MEMORY_WINDOW
title: PCMCIA_MODIFY_MEMORY_WINDOW
author: windows-driver-content
description: The PCMCIA_MODIFY_MEMORY_WINDOW interface routine sets the attributes of a memory window for a PCMCIA memory card. The memory window is mapped by the PCMCIA bus driver.
old-location: pcmcia\pcmcia_modify_memory_window.htm
old-project: PCMCIA
ms.assetid: 01469cd7-a023-42b0-9306-fc390bf990e6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _PAR_SET_INFORMATION, PAR_SET_INFORMATION, *PPAR_SET_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddpcm.h
req.include-header: Ntddpcm.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ModifyMemoryWindow
req.alt-loc: ntddpcm.h
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
req.typenames: PAR_SET_INFORMATION, *PPAR_SET_INFORMATION
---

# PCMCIA_MODIFY_MEMORY_WINDOW callback



## -description
The <b>PCMCIA_MODIFY_MEMORY_WINDOW</b> interface routine sets the attributes of a memory window for a PCMCIA memory card. The memory window is mapped by the PCMCIA bus driver.



## -prototype

````
PCMCIA_MODIFY_MEMORY_WINDOW ModifyMemoryWindow;

BOOLEAN ModifyMemoryWindow(
  _In_opt_ PVOID     Context,
  _In_     ULONGLONG HostBase,
  _In_     ULONGLONG CardBase,
  _In_     BOOLEAN   Enable,
  _In_opt_ ULONG     WindowSize,
  _In_opt_ UCHAR     AccessSpeed,
  _In_opt_ UCHAR     BusWidth,
  _In_opt_ BOOLEAN   AttributeMemory
)
{ ... }
````


## -parameters

### -param Context [in, optional]

Pointer to the context for the interface routine.


### -param HostBase [in]

Specifies the physical memory window to map. <i>HostBase</i> is the base address for the memory card in the system's physical address space.


### -param CardBase [in]

Specifies the byte offset in the PC Card's or CardBus card's memory where the memory mapping begins.


### -param Enable [in]

Specifies permission to access the memory window. If <i>Enable</i> is <b>TRUE</b>, memory access is permitted, otherwise memory access is not permitted.


### -param WindowSize [in, optional]

Specifies the size, in bytes, of the memory window that is mapped. The value of <i>WindowSize</i> cannot exceed the memory window granted to the driver in its assigned resources. If the value of Enable is <b>TRUE</b> and the value of WindowSize is zero, the size of the memory window granted to the driver in its assigned resources is used. If <i>Enable</i> is <b>FALSE</b>, <i>WindowSize</i> is not used.


### -param AccessSpeed [in, optional]

Specifies the access speed of the PC Card or CardBus card. The value of <i>AccessSpeed</i> is encoded as specified by the <i>PC Card Standard, Release 6.1</i>. If Enable is <b>FALSE</b>, <i>AccessSpeed</i> is not used.


### -param BusWidth [in, optional]

Specifies the width of bus access to the PCMCIA memory card. <i>BusWidth</i> must be one of the following values:




### -param PCMCIA_MEMORY_8BIT_ACCESS

</dl>
If <i>Enable</i> is <b>FALSE</b>, <i>BusWidth</i> is not used.


### -param AttributeMemory [in, optional]

Must be <b>FALSE</b> for common memory and <b>TRUE</b> for attribute memory. 


## -returns
The <b>PCMCIA_MODIFY_MEMORY_WINDOW</b> interface routine returns <b>TRUE</b> if the memory window is successfully enabled or disabled, as specified by the <i>Enable</i> parameter.


## -remarks
A caller must set the <i>Context</i> parameter to the context that is specified by the PCMCIA bus driver. The PCMCIA bus driver returns the context for the interface routines in the <b>Context</b> member of the same PCMCIA_INTERFACE_STANDARD structure that contains the pointers to the interface routines. If the <i>Context</i> parameter is not valid, system behavior is not defined, and the system might halt.

Callers of this routine must be running at IRQL &lt;= DISPATCH_LEVEL. To maintain overall system performance, it is recommended that drivers call this routine at IRQL &lt; DISPATCH_LEVEL.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537609">PCMCIA_IS_WRITE_PROTECTED</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537611">PCMCIA_SET_VPP</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCMCIA\buses]:%20PCMCIA_MODIFY_MEMORY_WINDOW callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

