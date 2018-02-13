---
UID: NF:ndis.NdisReadRegisterUshort
title: NdisReadRegisterUshort macro
author: windows-driver-content
description: NdisReadRegisterUshort is called by the miniport driver to read a USHORT from a memory-mapped device register.
old-location: netvista\ndisreadregisterushort.htm
old-project: netvista
ms.assetid: 0048fb18-8728-4b41-b4e2-5762966d5ed0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: miniport_register_ref_7eef891a-3f3e-4c42-8165-399555eb018f.xml, netvista.ndisreadregisterushort, NdisReadRegisterUshort, ndis/NdisReadRegisterUshort, NdisReadRegisterUshort macro [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReadRegisterUshort (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReadRegisterUshort (NDIS   5.1)) in Windows XP.
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
req.lib: ndis.h
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisReadRegisterUshort
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisReadRegisterUshort macro


## -description


<b>NdisReadRegisterUshort</b> is called by the miniport driver to read a USHORT from a memory-mapped device
  register.


## -syntax


````
VOID NdisReadRegisterUshort(
  [in]  PUSHORT Register,
  [out] PUSHORT Data
);
````


## -parameters




### -param Register [in]

Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>.


### -param Data [out]

Pointer to the caller-supplied variable in which this function returns the USHORT read from 
     <i>Register</i> .


## -remarks



If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.




## -see-also

<a href="..\ndis\nf-ndis-ndisreadregisterulong.md">NdisReadRegisterUlong</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>



<a href="..\ndis\nf-ndis-ndisreadregisteruchar.md">NdisReadRegisterUchar</a>



<a href="..\ndis\nf-ndis-ndiswriteregisterushort.md">NdisWriteRegisterUshort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisReadRegisterUshort macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

