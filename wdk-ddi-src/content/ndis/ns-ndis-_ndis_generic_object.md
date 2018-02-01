---
UID: NS:ndis._NDIS_GENERIC_OBJECT
title: "_NDIS_GENERIC_OBJECT"
author: windows-driver-content
description: The NDIS_GENERIC_OBJECT structure defines a generic object which a software component can use to obtain an NDIS handle.
old-location: netvista\ndis_generic_object.htm
old-project: netvista
ms.assetid: 1e7af434-a6ad-44c8-a33d-adebb53b8e1d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_GENERIC_OBJECT structure [Network Drivers Starting with Windows Vista], PNDIS_GENERIC_OBJECT, *PNDIS_GENERIC_OBJECT, ndis/PNDIS_GENERIC_OBJECT, ndis/NDIS_GENERIC_OBJECT, NDIS_GENERIC_OBJECT, _NDIS_GENERIC_OBJECT, ndis_object_ref_19f8706c-633c-4c32-9d86-17edc4e2ad12.xml, PNDIS_GENERIC_OBJECT structure pointer [Network Drivers Starting with Windows Vista], netvista.ndis_generic_object
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
-	NDIS_GENERIC_OBJECT
product: Windows
targetos: Windows
req.typenames: "*PNDIS_GENERIC_OBJECT, NDIS_GENERIC_OBJECT"
---

# _NDIS_GENERIC_OBJECT structure


## -description


The NDIS_GENERIC_OBJECT structure defines a generic object which a software component can use to
  obtain an NDIS handle.


## -syntax


````
typedef struct _NDIS_GENERIC_OBJECT {
  NDIS_OBJECT_HEADER Header;
  PVOID              Caller;
  PVOID              CallersCaller;
  PDRIVER_OBJECT     DriverObject;
} NDIS_GENERIC_OBJECT, *PNDIS_GENERIC_OBJECT;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     generic object structure (NDIS_GENERIC_OBJECT). NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_GENERIC_OBJECT, the 
     <b>Revision</b> member to NDIS_GENERIC_OBJECT_REVISION_1, and the 
     <b>Size</b> member to 
     sizeof(NDIS_GENERIC_OBJECT).


### -field Caller

Reserved for NDIS.


### -field CallersCaller

Reserved for NDIS.


### -field DriverObject

The driver object that is associated with the generic object. If there is no driver object, this
     member is <b>NULL</b>. This is the value passed at the 
     <i>DriverObject</i> parameter of the 
     <a href="..\ndis\nf-ndis-ndisallocategenericobject.md">
     NdisAllocateGenericObject</a> function.


## -remarks


Software components that do not already have an NDIS handle call 
    <a href="..\ndis\nf-ndis-ndisallocategenericobject.md">NdisAllocateGenericObject</a> to
    create a generic object. Such components use the handle obtained from 
    <b>NdisAllocateGenericObject</b> to allocate NDIS resources.

The 
    <i>Size</i> parameter of 
    <b>NdisAllocateGenericObject</b> specifies an amount of memory, in bytes, to reserve for the caller. 
    <b>NdisAllocateGenericObject</b> adds the additional memory after the NDIS_OBJECT_STRUCTURE members.

Most NDIS drivers do not require a generic object to get a handle. NDIS protocol, intermediate, and
    miniport drivers obtain a handle during initialization.

Use the 
    <a href="..\ndis\nf-ndis-ndisfreegenericobject.md">NdisFreeGenericObject</a> function to
    free a generic object that was created with 
    <b>NdisAllocateGenericObject</b>.



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\ndis\nf-ndis-ndisfreegenericobject.md">NdisFreeGenericObject</a>

<a href="..\ndis\nf-ndis-ndisallocategenericobject.md">NdisAllocateGenericObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_GENERIC_OBJECT structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

