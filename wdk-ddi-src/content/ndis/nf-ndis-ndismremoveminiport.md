---
UID: NF:ndis.NdisMRemoveMiniport
title: NdisMRemoveMiniport function
author: windows-driver-content
description: The NdisMRemoveMiniport function removes the specified miniport driver adapter that the miniport driver has determined is unrecoverable from the system.
old-location: netvista\ndismremoveminiport.htm
tech.root: netvista
ms.assetid: 70745b03-f9a3-4398-b41a-dc75bd16ffe0
ms.date: 5/2/2018
ms.keywords: NdisMRemoveMiniport, NdisMRemoveMiniport function [Network Drivers Starting with Windows Vista], miniport_ndis_functions_ref_54f3a264-7933-4dca-86f4-42652abe9a9a.xml, ndis/NdisMRemoveMiniport, netvista.ndismremoveminiport
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 5.1, and NDIS 6.0 and later. For NDIS 5.1 drivers, see    NdisMRemoveMiniport (NDIS   5.1).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMRemoveMiniport
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMRemoveMiniport function


## -description


The
  <b>NdisMRemoveMiniport</b> function removes the specified miniport driver adapter that the miniport driver
  has determined is unrecoverable from the system.


## -parameters




### -param MiniportHandle

The handle to the initialized miniport adapter that the miniport driver has determined is
     unrecoverable.


## -returns



<b>NdisMRemoveMiniport</b> can return either of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The miniport adapter has been removed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
An attempt to remove the miniport adapter failed.

</td>
</tr>
</table>
 




## -remarks



If a miniport driver has determined that a particular miniport adapter has failed and is
    unrecoverable, the miniport driver can call 
    <b>NdisMRemoveMiniport</b> to remove the miniport adapter from the local computer system. In this call,
    the miniport driver passes the handle to the miniport adapter to remove.

For example, if a miniport driver detects that a miniport adapter is resetting very frequently and is
    causing the computer to freeze every few seconds, the driver can request NDIS to remove the miniport
    adapter.



