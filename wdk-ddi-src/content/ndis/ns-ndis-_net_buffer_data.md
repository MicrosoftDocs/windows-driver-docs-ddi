---
UID: NS:ndis._NET_BUFFER_DATA
title: "_NET_BUFFER_DATA"
author: windows-driver-content
description: The NET_BUFFER_DATA structure contains information for managing the data buffers that are attached to a NET_BUFFER structure, and it identifies the next NET_BUFFER structure in a list of NET_BUFFER structures.
old-location: netvista\net_buffer_data.htm
old-project: netvista
ms.assetid: d1b5e1c7-5ade-4f54-a5f1-200420964f0e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNET_BUFFER_DATA, NET_BUFFER_DATA, NET_BUFFER_DATA structure [Network Drivers Starting with Windows Vista], PNET_BUFFER_DATA, PNET_BUFFER_DATA structure pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER_DATA, ndis/NET_BUFFER_DATA, ndis/PNET_BUFFER_DATA, ndis_netbuf_structures_ref_3e603c77-b97e-4c1f-9fee-e874e741a543.xml, netvista.net_buffer_data"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NET_BUFFER_DATA
product: Windows
targetos: Windows
req.typenames: NET_BUFFER_DATA, *PNET_BUFFER_DATA
---

# _NET_BUFFER_DATA structure


## -description


The NET_BUFFER_DATA structure contains information for managing the data buffers that are attached to
  a NET_BUFFER structure, and it identifies the next 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure in a list of NET_BUFFER
  structures.


## -syntax


````
typedef struct _NET_BUFFER_DATA {
  PNET_BUFFER            Next;
  PMDL                   CurrentMdl;
  ULONG                  CurrentMdlOffset;
  NET_BUFFER_DATA_LENGTH NbDataLength;
  PMDL                   MdlChain;
  ULONG                  DataOffset;
} NET_BUFFER_DATA, *PNET_BUFFER_DATA;
````


## -struct-fields




### -field Next

A pointer to the next NET_BUFFER structure in a linked list of NET_BUFFER structures. If this
     structure is the last NET_BUFFER structure in the list, this member is <b>NULL</b>.


### -field CurrentMdl

A pointer to the first MDL that the current driver is using. This member provides an optimization
     that improves performance by skipping over any MDLs that the current driver is not using.


### -field CurrentMdlOffset

The offset, in bytes, to the beginning of the 
     <i>used data space</i> in the MDL that is specified by the 
     <b>CurrentMdl</b> member.


### -field NbDataLength

The length, in bytes, of the used data space in the MDL chain. The maximum length is 0xFFFFFFFF
     bytes.


### -field MdlChain

A pointer to a linked list of MDLs that map a data buffer. The data buffer stores the network
     data.


### -field DataOffset

The offset, in bytes, from the beginning of the MDL chain to the beginning of the network data in
     the MDL chain. This offset is also the size, in bytes, of the 
     <i>unused data space</i>.


## -remarks



The 
    <a href="..\ndis\ns-ndis-_net_buffer_header.md">NET_BUFFER_HEADER</a> structure contains a
    NET_BUFFER_DATA structure that defines data for the 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure. To access the members of
    NET_BUFFER_DATA, use the 
    <a href="..\ndis\nf-ndis-ndisretreatnetbufferdatastart.md">
    NdisRetreatNetBufferDataStart</a> and 
    <a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
    NdisAdvanceNetBufferDataStart</a> functions, and the following macros:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff568416">NET_BUFFER_NEXT_NB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568386">NET_BUFFER_FIRST_MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568383">NET_BUFFER_DATA_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568382">NET_BUFFER_DATA_LENGTH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568379">NET_BUFFER_CURRENT_MDL</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568380">
       NET_BUFFER_CURRENT_MDL_OFFSET</a>


<div class="alert"><b>Note</b>  The C and C++ compilers use different definitions for these macros. Failure to use
    the macros can cause problems when switching compilers.</div>
<div> </div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568416">NET_BUFFER_NEXT_NB</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568380">NET_BUFFER_CURRENT_MDL_OFFSET</a>



<a href="..\ndis\ns-ndis-_net_buffer_header.md">NET_BUFFER_HEADER</a>



<a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
   NdisAdvanceNetBufferDataStart</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568379">NET_BUFFER_CURRENT_MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568382">NET_BUFFER_DATA_LENGTH</a>



<a href="..\ndis\nf-ndis-ndisretreatnetbufferdatastart.md">
   NdisRetreatNetBufferDataStart</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568386">NET_BUFFER_FIRST_MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568383">NET_BUFFER_DATA_OFFSET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_BUFFER_DATA structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

