---
UID: NF:ndis.NdisFRestartFilter
title: NdisFRestartFilter function
author: windows-driver-content
description: A filter driver calls the NdisFRestartFilter function to request NDIS to initiate a restart operation for a filter module.
old-location: netvista\ndisfrestartfilter.htm
old-project: netvista
ms.assetid: 8b0fc032-3ec0-4e18-a5f5-6409db8ae42d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisFRestartFilter
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
req.alt-api: NdisFRestartFilter
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Filter_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFRestartFilter function



## -description
A filter driver calls the
  <b>NdisFRestartFilter</b> function to request NDIS to initiate a restart operation for a filter
  module.



## -syntax

````
NDIS_STATUS NdisFRestartFilter(
  _In_ NDIS_HANDLE NdisFilterHandle
);
````


## -parameters

### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


## -returns
<b>NdisFRestartFilter</b> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
<a href="..\ndis\nf-ndis-ndisfrestartfilter.md">NdisFRestartFilter</a> returns NDIS_STATUS_SUCCESS if it started the restart operation.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
<a href="..\ndis\nf-ndis-ndisfrestartfilter.md">NdisFRestartFilter</a> failed because of insufficient resources.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
<a href="..\ndis\nf-ndis-ndisfrestartfilter.md">NdisFRestartFilter</a> returns NDIS_STATUS_FAILURE if none of the preceding values applies.

 


## -remarks
The filter driver can change the filter module attributes at run time by calling the 
    <b>NdisFRestartFilter</b> function. 
    <b>NdisFRestartFilter</b> schedules a pause and then a restart operation for the specified filter
    module.

Before NDIS restarts the filter module, it calls the 
    <a href="..\ndis\nc-ndis-filter_set_module_options.md">FilterSetModuleOptions</a> function for the filter module. From 
    its <i>FilterSetModuleOptions</i> function, the filter driver can change the data handlers for that filter module by
    calling the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function
    and specifying a new set of handlers.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_set_module_options.md">FilterSetModuleOptions</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFRestartFilter function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

