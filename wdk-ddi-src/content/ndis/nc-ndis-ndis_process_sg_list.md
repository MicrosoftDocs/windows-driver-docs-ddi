---
UID: NC:ndis.NDIS_PROCESS_SG_LIST
title: NDIS_PROCESS_SG_LIST
author: windows-driver-content
description: The NetProcessSGList function (NDIS_PROCESS_SG_LIST_HANDLER entry point) processes a scatter/gather list.
old-location: netvista\netprocesssglist.htm
old-project: netvista
ms.assetid: 5b99e0ec-7c82-46d6-b32a-246b368cf4f1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.netprocesssglist, NetProcessSGList callback function [Network Drivers Starting with Windows Vista], NetProcessSGList, NDIS_PROCESS_SG_LIST, NDIS_PROCESS_SG_LIST, ndis/NetProcessSGList, ndis_shared_memory_ref_0c3e2851-6897-4997-a974-2a108e1e5ee9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.irql: "= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	NetProcessSGList
product: Windows
targetos: Windows
req.typenames: "*LPVIDEO_STREAM_INIT_PARMS, VIDEO_STREAM_INIT_PARMS"
---

# NDIS_PROCESS_SG_LIST callback


## -description


The 
  <i>NetProcessSGList</i> function (NDIS_PROCESS_SG_LIST_HANDLER entry point) processes a scatter/gather
  list.


## -prototype


````
NDIS_PROCESS_SG_LIST NetProcessSGList;

VOID NetProcessSGList(
  _In_ PDEVICE_OBJECT       DeviceObject,
  _In_ PVOID                Reserved,
  _In_ PSCATTER_GATHER_LIST ScatterGatherListBuffer,
  _In_ PVOID                Context
)
{ ... }
````


## -parameters




### -param DeviceObject [in]

A pointer to a 
     <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure.


### -param Reserved [in]

Reserved for NDIS.


### -param ScatterGatherListBuffer [in]

A pointer to a 
     <a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a> structure.


### -param Context [in]

A pointer to a block of driver-allocated context information that contains information about the
     scatter gather list. The driver provided this context information in the 
     <b>Context</b> member of the 
     <a href="..\ndis\ns-ndis-_ndis_scatter_gather_list_parameters.md">
     NDIS_SCATTER_GATHER_LIST_PARAMETERS</a> structure.


## -returns



None




## -remarks



NDIS calls the 
    <i>NetProcessSGList</i> function that is specified at the 
    <b>ProcessSGListHandler</b> member of the 
    <a href="..\ndis\ns-ndis-_ndis_scatter_gather_list_parameters.md">
    NDIS_SCATTER_GATHER_LIST_PARAMETERS</a> structure within the context of the 
    <a href="..\ndis\nf-ndis-ndisbuildscattergatherlist.md">
    NdisBuildScatterGatherList</a> function.

The driver specified the entry point (NDIS_PROCESS_SG_LIST_HANDLER) for 
    <i>NetProcessSGList</i> in the NDIS_SCATTER_GATHER_LIST_PARAMETERS structure.




## -see-also

<a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\ndis\ns-ndis-_ndis_scatter_gather_list_parameters.md">
   NDIS_SCATTER_GATHER_LIST_PARAMETERS</a>



<a href="..\ndis\nf-ndis-ndisbuildscattergatherlist.md">NdisBuildScatterGatherList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PROCESS_SG_LIST callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

