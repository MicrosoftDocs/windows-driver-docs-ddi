---
UID: NS:ndis._NDIS_FILTER_PAUSE_PARAMETERS
title: "_NDIS_FILTER_PAUSE_PARAMETERS"
author: windows-driver-content
description: The NDIS_FILTER_PAUSE_PARAMETERS structure defines the pause parameters for the filter module.
old-location: netvista\ndis_filter_pause_parameters.htm
old-project: netvista
ms.assetid: 070c6d5d-9942-4bff-8894-9aa69d5e7983
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_FILTER_PAUSE_PARAMETERS, NDIS_FILTER_PAUSE_PARAMETERS, NDIS_FILTER_PAUSE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_FILTER_PAUSE_PARAMETERS, PNDIS_FILTER_PAUSE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_FILTER_PAUSE_PARAMETERS, filter_structures_ref_78bd5df6-c235-4af1-9b2f-1ddce38a0017.xml, ndis/NDIS_FILTER_PAUSE_PARAMETERS, ndis/PNDIS_FILTER_PAUSE_PARAMETERS, netvista.ndis_filter_pause_parameters"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_FILTER_PAUSE_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_FILTER_PAUSE_PARAMETERS, *PNDIS_FILTER_PAUSE_PARAMETERS
---

# _NDIS_FILTER_PAUSE_PARAMETERS structure


## -description


The NDIS_FILTER_PAUSE_PARAMETERS structure defines the pause parameters for the filter module.


## -syntax


````
typedef struct _NDIS_FILTER_PAUSE_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              PauseReason;
} NDIS_FILTER_PAUSE_PARAMETERS, *PNDIS_FILTER_PAUSE_PARAMETERS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_FILTER_PAUSE_PARAMETERS structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_PAUSE_PARAMETERS, the 
     <b>Revision</b> member to NDIS_FILTER_PAUSE_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_FILTER_PAUSE_PARAMETERS_REVISION_1.


### -field Flags

Reserved.


### -field PauseReason

<div class="alert"><b>Note</b>  This member is deprecated for NDIS 6.40 and later drivers.</div>
<div> </div>
The value will always be NDIS_PAUSE_NDIS_INTERNAL.


## -remarks



To define filter module pause parameters, NDIS passes a pointer to an NDIS_FILTER_PAUSE_PARAMETERS
    structure to the 
    <a href="..\ndis\nc-ndis-filter_pause.md">FilterPause</a> function.




## -see-also

<a href="..\ndis\nc-ndis-filter_pause.md">FilterPause</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_FILTER_PAUSE_PARAMETERS structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

