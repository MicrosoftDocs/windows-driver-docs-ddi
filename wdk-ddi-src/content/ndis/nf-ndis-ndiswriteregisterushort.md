---
UID: NF:ndis.NdisWriteRegisterUshort
title: NdisWriteRegisterUshort macro
author: windows-driver-content
description: NdisWriteRegisterUshort is called by the miniport driver to write a USHORT to a memory-mapped device register.
old-location: netvista\ndiswriteregisterushort.htm
old-project: netvista
ms.assetid: 676beebf-4c22-4eb5-bfad-a6f66f3a95be
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisWriteRegisterUshort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteRegisterUshort (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteRegisterUshort (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisWriteRegisterUshort
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisWriteRegisterUshort macro



## -description
<b>NdisWriteRegisterUshort</b> is called by the miniport driver to write a USHORT to a memory-mapped device
  register.



## -syntax

````
VOID NdisWriteRegisterUshort(
  [in] PUSHORT Register,
  [in] USHORT  Data
);
````


## -parameters

### -param Register [in]

Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>.


### -param Data [in]

Specifies the caller-supplied USHORT that this function transfers to the 
     <i>Register</i> .


## -remarks
If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreadregisterushort.md">NdisReadRegisterUshort</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiswriteregisteruchar.md">NdisWriteRegisterUchar</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiswriteregisterulong.md">NdisWriteRegisterUlong</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisWriteRegisterUshort macro%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

