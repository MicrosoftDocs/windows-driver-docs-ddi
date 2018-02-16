---
UID: NF:ndis.NdisFSetAttributes
title: NdisFSetAttributes function
author: windows-driver-content
description: A filter driver calls the NdisFSetAttributes function to specify a filter module context area.
old-location: netvista\ndisfsetattributes.htm
old-project: netvista
ms.assetid: 66e20ac3-e97d-429d-868e-79c04881702b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: filter_ndis_functions_ref_67ad6b8c-e7ae-45d7-9213-48e8a2b6c2ff.xml, NdisFSetAttributes, NdisFSetAttributes function [Network Drivers Starting with Windows Vista], netvista.ndisfsetattributes, ndis/NdisFSetAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Filter_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisFSetAttributes
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisFSetAttributes function


## -description


A filter driver calls the 
  <b>NdisFSetAttributes</b> function to specify a filter module context area.


## -syntax


````
NDIS_STATUS NdisFSetAttributes(
  _In_ NDIS_HANDLE             NdisFilterHandle,
  _In_ NDIS_HANDLE             FilterModuleContext,
  _In_ PNDIS_FILTER_ATTRIBUTES FilterAttributes
);
````


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param FilterModuleContext [in]

The caller-allocated context area for this filter module.


### -param FilterAttributes [in]

A pointer to a filter driver allocated 
     <a href="..\ndis\ns-ndis-_ndis_filter_attributes.md">
     NDIS_FILTER_ATTRIBUTES</a> structure.


## -returns



<b>NdisFSetAttributes</b> returns one of the following status values:

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
<b>NdisFSetAttributes</b> returns NDIS_STATUS_SUCCESS if it set the filter driver attributes.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisFSetAttributes</b> failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisFSetAttributes</b> returns NDIS_STATUS_FAILURE if none of the preceding values applies.

</td>
</tr>
</table>
 




## -remarks



A filter driver calls 
    <b>NdisFSetAttributes</b> from its 
    <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function and passes the
    handle that NDIS passed to 
    <i>FilterAttach</i> at the 
    <i>NdisFilterHandle</i> parameter. The 
    <i>FilterModuleContext</i> parameter of 
    <b>NdisFSetAttributes</b> specifies the context area for this filter module. NDIS passes the context area
    back to the filter driver in calls to functions such as 
    <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">FilterSendNetBufferLists</a>.




## -see-also

<a href="..\ndis\ns-ndis-_ndis_filter_attributes.md">NDIS_FILTER_ATTRIBUTES</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">FilterSendNetBufferLists</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFSetAttributes function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

