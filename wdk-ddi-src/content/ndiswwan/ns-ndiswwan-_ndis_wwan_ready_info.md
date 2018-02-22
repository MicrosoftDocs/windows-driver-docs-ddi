---
UID: NS:ndiswwan._NDIS_WWAN_READY_INFO
title: "_NDIS_WWAN_READY_INFO"
author: windows-driver-content
description: The NDIS_WWAN_READY_INFO structure represents the ready-state of the MB device and Subscriber Identity Module (SIM card).
old-location: netvista\ndis_wwan_ready_info.htm
old-project: netvista
ms.assetid: 9f47b70a-426c-47a2-b438-fc00eadc002f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "_NDIS_WWAN_READY_INFO, *PNDIS_WWAN_READY_INFO, ndiswwan/PNDIS_WWAN_READY_INFO, PNDIS_WWAN_READY_INFO, NDIS_WWAN_READY_INFO, NDIS_WWAN_READY_INFO structure [Network Drivers Starting with Windows Vista], netvista.ndis_wwan_ready_info, WwanRef_6ae45c84-c13d-4142-b39a-07b3a9f57253.xml, ndiswwan/NDIS_WWAN_READY_INFO, PNDIS_WWAN_READY_INFO structure pointer [Network Drivers Starting with Windows Vista]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndiswwan.h
apiname:
-	NDIS_WWAN_READY_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_READY_INFO, *PNDIS_WWAN_READY_INFO
---

# _NDIS_WWAN_READY_INFO structure


## -description


The NDIS_WWAN_READY_INFO structure represents the ready-state of the MB device and Subscriber
  Identity Module (SIM card).


## -syntax


````
typedef struct _NDIS_WWAN_READY_INFO {
  NDIS_OBJECT_HEADER Header;
  WWAN_READY_INFO    ReadyInfo;
} NDIS_WWAN_READY_INFO, *PNDIS_WWAN_READY_INFO;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_READY_INFO structure. The
     MB Service sets the header with the values that are shown in the following table when it sends the data
     structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     

<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
Type

</td>
<td>
NDIS_OBJECT_TYPE_DEFAULT

</td>
</tr>
<tr>
<td>
Revision

</td>
<td>
NDIS_WWAN_READY_INFO_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_READY_INFO)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field ReadyInfo

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_ready_info.md">WWAN_READY_INFO</a> object that represents the
     device ready-state.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_ready_info.md">WWAN_READY_INFO</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_READY_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

