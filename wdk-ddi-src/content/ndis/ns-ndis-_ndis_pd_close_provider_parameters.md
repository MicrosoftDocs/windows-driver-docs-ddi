---
UID: NS:ndis._NDIS_PD_CLOSE_PROVIDER_PARAMETERS
title: "_NDIS_PD_CLOSE_PROVIDER_PARAMETERS"
author: windows-driver-content
description: This structure represents the parameters that are used when calling the OID_PD_CLOSE_PROVIDER OID.
old-location: netvista\ndis_pd_close_provider_parameters.htm
old-project: netvista
ms.assetid: 9C33CA12-E725-4634-A1EC-0A919987BA6E
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDIS_PD_CLOSE_PROVIDER_PARAMETERS, netvista.ndis_pd_close_provider_parameters, ndis/NDIS_PD_CLOSE_PROVIDER_PARAMETERS, NDIS_PD_CLOSE_PROVIDER_PARAMETERS structure [Network Drivers Starting with Windows Vista], _NDIS_PD_CLOSE_PROVIDER_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	Ndis.h
apiname:
-	NDIS_PD_CLOSE_PROVIDER_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_PD_CLOSE_PROVIDER_PARAMETERS
---

# _NDIS_PD_CLOSE_PROVIDER_PARAMETERS structure


## -description


This structure represents the parameters that are used when calling the <a href="https://msdn.microsoft.com/library/windows/hardware/dn931851">OID_PD_CLOSE_PROVIDER</a> OID.


## -syntax


````
typedef struct _NDIS_PD_CLOSE_PROVIDER_PARAMETERS {
  NDIS_OBJECT_HEADER      Header;
  ULONG                   Flags;
  NDIS_PD_PROVIDER_HANDLE ProviderHandle;
} NDIS_PD_CLOSE_PROVIDER_PARAMETERS;
````


## -struct-fields




### -field Header

The <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_CLOSE_PROVIDER_PARAMETERS</b> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_CLOSE_PROVIDER_PARAMETERS_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_CLOSE_PROVIDER_PARAMETERS_REVISION_1</b></li>
</ul>

### -field Flags

This member is reserved and must be set to 0.


### -field ProviderHandle

A provider handle that identifies the PD-capable miniport driver's provider object.


## -remarks



This structure must be aligned on an 8-byte boundary.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn931851">OID_PD_CLOSE_PROVIDER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PD_CLOSE_PROVIDER_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

